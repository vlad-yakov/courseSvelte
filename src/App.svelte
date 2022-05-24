<svelte:head>
    <!--<link rel="stylesheet" href="https://unpkg.com/flickity@2.3.0/dist/flickity.css">
        <script src="https://unpkg.com/flickity@2.3.0/dist/flickity.pkgd.js"></script>-->
    </svelte:head>

    <Drawer variant="modal"  bind:open  transitionDuration={1000}>
        <Content>
            <p>Найти</p>
            <Autocomplete
                    search={searchItems}
            >
                <Text
                        slot="loading"
                        style="display: flex; width: 100%; justify-content: center; align-items: center;"
                >
                    <CircularProgress style="height: 24px; width: 24px;" indeterminate />
                </Text>

            </Autocomplete>
            <div id="reply">

            </div>
        </Content>
    </Drawer>

<Router>
        <div class="stat" on:click={WindowClick}>
            <header>
                <button id="menu" on:click={menuClick} aria-expanded=false name="menu">
                    <svg width="28px" height="28px" aria-hidden="false">
                        <polyline
                                points="8 3 20 14 8 25"
                                stroke-width='3'
                                stroke='black'
                                stroke-linecap="round"
                                fill="none"
                                stroke-linejoin="round"
                        />
                    </svg>
                </button>
                <h3 on:click={SlideUp}>
                    СЛЕД
                </h3>
                <button id="find" on:click={SearchClick} name="search">
                    <svg width="28px" height="28px">
                        <circle
                                cx="10"
                                cy="10"
                                r="8"
                                fill="none"
                                stroke="black"
                                stroke-width="3"
                        />
                        <line
                                x1='14' y1="17"
                                x2='20' y2='26'
                                stroke-width="3"
                                stroke="black"
                                stroke-linecap="round"

                        />
                    </svg >
                </button>

            </header>

            <nav>
                <div>
                    <Link to="/"><p>холл</p></Link>
                    &#47
                    <Link to="art"><p>худЗал</p></Link>
                    &#47
                    <Link to="liter"><p>литЗал</p></Link>
                    &#47
                    <Link to="photo"><p>фотоЗал</p></Link>
                    &#47
                    <Link to="forum"><p>форум</p></Link>
            </div>
        </nav>
    </div>

<div id="app" on:click={WindowClick}>

    <main>

        <TransitionContainer>
            <Route path="/" primary={false}>
                <RouteTransition x={330} duration={900}>
                    <Lobby/>
                </RouteTransition>
            </Route>

            <Route path="art" primary={false}>
                <RouteTransition x={330} duration={900}>
                    <Arthall/>
                </RouteTransition>
            </Route>
        </TransitionContainer>

    </main>

    <footer>
        <hr>
        <div>
            <p>
                <abbr>
                    сд
                </abbr><br>
                культжурнал про искусство СНГ<br>
                &#169 2022
            </p>

            <div>
                <div class="social vk">
                    <a href="https://vk.com/vlad_yakovlev28" target="_blank">
                        <i class="fa fa-vk" /></a
                    >
                </div>
                <div class="social tg">
                    <a href="https://t.me/v_yakov" target="_blank"
                    ><i class="fa fa-paper-plane "/></a
                    >
                </div>
                <div class="social pinterest">
                    <a href="https://www.pinterest.ru/vladyak99/_created" target="_blank"
                    ><i class="fa fa-pinterest fa"/></a
                    >
                </div>
            </div>

            <p class="police">
                <a href="https://docs.google.com/document/d/1fP47bg6Q3xvC3bVFVge4P3xIPsAQvAtsyUuvWh3oC9U/edit?usp=sharing"
                   target="_blank">Условия использования</a>
                <br>
                <a href="https://docs.google.com/document/d/1fP47bg6Q3xvC3bVFVge4P3xIPsAQvAtsyUuvWh3oC9U/edit?usp=sharing"
                   target="_blank">Для публикации</a>
            </p>
        </div>
    </footer>

</div>
</Router>

<script>
    import { Router, Route, Link } from "svelte-navigator";
    import Lobby from "./lobby.svelte";
    import Arthall from "./arthall.svelte";
    import Lithall from "./lithall.svelte";
    import Photohall from "./photohall.svelte";
    import Forum from "./forum.svelte";

    import RouteTransition from "./RouteTransition.svelte";
    import TransitionContainer from "./TransitionContainer.svelte";

    import Drawer, {
        Content
    } from '@smui/drawer';
    import Autocomplete from '@smui-extra/autocomplete';
    import { Text } from '@smui/list';
    import CircularProgress from '@smui/circular-progress';

    let open = false;

    async function searchItems(input) {
        let counter = 0;
        if (input === '') {
            return [];
        }

        // Pretend to have some sort of canceling mechanism.
        const myCounter = ++counter;

        // Pretend to be loading something...
        await new Promise((resolve) => setTimeout(resolve, 1000));

        if (myCounter !== counter) {
            // This means the function was called again, so we should cancel.
            // This is how you tell Autocomplete to cancel this search. It won't
            // replace the results of any subsequent search that has already finished.
            return false;
        }

        // Return a list of matches.
        return resolve.filter((item) =>
            item.toLowerCase().includes(input.toLowerCase())
        );
    }

    function menuClick() {
        let btn = document.body.querySelector('button');
        let target = document.body.querySelector('nav');
        let expanded = (btn.getAttribute(`aria-expanded`) === "true" || false);
        let prime = document.body.querySelector('#app');
        let vector = document.body.querySelector('svg');
        let anchor = document.body.querySelectorAll('#anchorby, #anchorukr, #anchorrus')
        //инвертируем значение по клику
        btn.setAttribute(`aria-expanded`, !expanded);
        if(!expanded) {
            window.$('nav').slideToggle(330);
            target.style.display = 'block';
            target.style.overflow = 'hidden';
            prime.style.top = '105px';
            vector.ariaHidden = 'true';
            vector.style.transform = 'rotate(90deg)';
            anchor.forEach(an => an.style.top = '-105px');

        } else {
            target.style.overflow = 'visible';
            window.$('nav').slideToggle(330)
            prime.style.top = '74px';
            vector.ariaHidden = 'false';
            vector.style.transform = 'rotate(0deg)';
            anchor.forEach(an => an.style.top = '-74px');
        }
    }

   function SlideUp() {
           window.$('html, body').animate({scrollTop: 0},330);
   }

    function SearchClick() {
        open = open ? false : true;
    }

    function WindowClick() {
        open = false
    }

</script>

<style lang="scss">

div.stat {
  position: fixed;
  width: 100%;
  z-index: 5;

  header {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    height: 74px;
    text-align: center;
    display: flex;
    justify-content: space-between;
    border: 10px solid #fff;
    background: #c7b592;

    button {
      margin: 0px;
      padding: 8px;
      border: none;
      background: transparent;
      flex: 1 1 3%;

      svg {
        vertical-align: middle;
        transition: .33s;
        transform-origin: center center;

        &:hover {
          opacity: 0.33;
        }
      }
    }

    h3 {
      flex: 1 1 90%;
      font: lighter 30px "Source Sans SemiBold";
      margin: 0px;
      color: black;
      padding: 8px;
    }
  }

  nav {
    display: none;
    background: #fff;
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);

    div {
      padding: 5px;
      display: flex;
      justify-content: center;

      p {
        padding: 0 4px;
        margin: 0;
        font: lighter 17px "Source Sans SemiBold";
        color: black;

        &:hover {
          transition: 330ms;
          color: #c7b592;
        }
      }
    }
  }
}

  div#app {
    margin: 0;
    padding: 0;
    position: relative;
    top: 74px;
    transition: top 330ms ease-in-out;
    font-size: 16px;

    main {
      text-align: left;
      padding: 0 15px;
      min-height: 559px;
      margin: 0;
      overflow: auto;

      &::-webkit-scrollbar {
        width: 0;
      }
    }

    footer {
      position: static;
      flex: 0 0 auto;
      bottom: 0;
      margin: 0px 10px 0px;
      color: black;
      height: 7em;
      background: white;

      div {
        margin: 7px;
        display: flex;
        flex-wrap: nowrap;
        justify-content: space-between;

        p {
          margin: 5px;
          line-height: 26px;
        }

        abbr {
          font-size: 170%;
          font-weight: bold;
        }

        .social a {
          text-align: center;
          line-height: 43px;
          font-size: 29px;
          width: 46px;
          height: 46px;
          float: left;
          border-radius: 23px;
          margin: 10px;
          color: #000;
          transition: 200ms;
        }

        .vk a:hover {
          transition: 200ms;
          color: #5d84ae;
          font-size: 32px;
        }

        .tg a {
          font-size: 24px;

          &:hover {
            transition: 200ms;
            color: #249bd7;
            font-size: 27px;
          }
        }

        .pinterest a:hover {
          transition: 200ms;
          color: #c8232c;
          font-size: 32px;
        }

        p.police {
          text-align: right;
          padding-top: 2px;

          a {
            line-height: 24px;
            color: #000;

            &:hover {
              transition: 150ms;
              color: #c7b592;
            }
          }
        }
      }
    }
  }

</style>
