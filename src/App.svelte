<Drawer variant="modal" bind:open>
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
        <hr>
    </Content>
</Drawer>
<div class="stat">
    <header>
    <button id="menu" on:click={menuClick} aria-expanded=false>
        <img src="../arrowright.png" width="28" height="28" alt="меню" />
    </button>
    <h3>
        СЛЕД
    </h3>
    <button id="find" on:click={SearchClick}>
        <img src="../search.png" width="28" height="28" alt="поиск" />
    </button>

</header>


<nav>
    <div>
        <a href="ros.svelte">худЗал</a>
        &#47
        <a href="bel.svelte">литЗал</a>
        &#47
        <a href="ukr.svelte">фотоЗал</a>
        &#47
        <a href="kvz.svelte">форум</a>
    </div>
</nav>
</div>
<div id="app">

    <main>
        <table>
            <tr>
                <td class="desk">
                    <h2>Вводное</h2>
                    <p>
                        Искусство может передавать смыслы. Это неограниченное пространство, в
                        котором возможно делать всё как ты сам захочешь. Как этот сайт написан на
                        каком-то языке программирования, эта статья изначально написана на русском,
                        так и каждый творец на своём уникальном языке передаёт важный для него
                        смысл. Это необычное представление наших мыслей, отчего и оценка смыслов
                        приобретает более яркий оттенок.<br>

                        Смыслов в СНГ очень много, в череде которых и веками нерешённые проблемы,
                        внутренние установки которые мы называем менталитетом, чувства которые
                        терзают многих из нас - это только часть того хаоса, происходящего в голове
                        выходца из бывших частей соцстраны и настоящих независимых и сильных держав.<br>

                        Этот сайт для каждого может нести разные цели. Для кого-то это место чтобы
                        проникнуться нашими национальными особенностями, некоторые здесь
                        задумываются о чём-то более вселенском. А кто-то хочет понять как мыслят
                        художники, какими вопросами забита их голова. Важно то, что здесь ты можешь
                        чем-то поделиться, поэтому более не задерживаю.

                    </p>
                </td>
            </tr>
        </table>
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
                        <i class="fa fa-vk" aria-hidden="true" /></a
                    >
                </div>
                <div class="social tg">
                    <a href="https://t.me/v_yakov" target="_blank"
                    ><i class="fa fa-paper-plane " aria-hidden="true" /></a
                    >
                </div>
                <div class="social pinterest">
                    <a href="https://www.pinterest.ru/vladyak99/_created" target="_blank"
                    ><i class="fa fa-pinterest fa" aria-hidden="true" /></a
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

<script>
    import Drawer, {
        Content,

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
        //инвертируем значение по клику
        btn.setAttribute(`aria-expanded`, !expanded);
        if(!expanded) {
            window.$('nav').slideToggle(330);
            target.style.display = 'block';
            target.style.overflow = 'hidden';
            prime.style.top = '105px';
        } else {
            target.style.overflow = 'visible';
            window.$('nav').slideToggle(330)
            prime.style.top = '74px';
        }
    }

    function SearchClick() {
        open = open ? false : true;
        /*
        .show();
        .hide()
         */
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

      img {
        vertical-align: middle;

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

    div {
      padding: 5px;
      display: flex;
      justify-content: center;

      a {
        padding: 0 4px;
        font: lighter 17px "Source Sans SemiBold";
        color: black;

        &:hover {
          transition: 150ms;
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

    main {
      font-size: 15px;
      text-align: center;
      padding: 0 15px;
      min-height: 29.2em;
      margin: 0;

      h2 {
        margin: 10px;
        text-transform: uppercase;
        font-size: 34px;
        font-weight: 500;
      }

      p {
        margin: 0px;
        padding: 0px;
      }
    }

    footer {
      position: static;
      flex: 0 0 auto;
      bottom: 0;
      font-size: 15px;
      margin: 0px 10px 0px;
      color: black;
      height: 7em;

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
          font-size: 165%;
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

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
