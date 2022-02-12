
<header>
    <div class="head">
        <div class="bttn">
            <button id="arrow"  on:click={menuClick} aria-expanded=false>
                <img id="strelka" src="../arrowright.png" width="28" height="28" alt="меню" />
            </button>
            <button id="menu">
                <h3>
                    СЛЕД
                </h3>
            </button>
        </div>
       <button>
               <img id="find" src="../search.png" width="28" height="28" alt="поиск" />
       </button>
    </div>
</header>

<nav id="map" hidden>
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

<main>
    <table>
        <tr>
            <td class="desk">
                <h2>В ОБЩЕМ</h2>
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
            <td class="actual">
                <div>

                </div>
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

<script>
    function menuClick() {
        let btn = document.body.querySelector('arrow');
        let target = document.body.querySelector('nav');
        let expanded = (btn.getAttribute(`aria-expanded`) === "true" || false);
        //инвертируем значение по клику
        btn.setAttribute(`aria-expanded`, !expanded);
        target.hidden = expanded;
    }

</script>

<style lang="scss">

  header {
    flex: 0 0 auto;
    text-align: center;
    margin: 10px;
    background: #c7b592;

    div.head {
      display: flex;
      flex-wrap: nowrap;
      justify-content: space-between;

      div.bttn {

      }

      button {
        margin: 0px;
        padding: 8px;
        border: none;
        background: transparent;
        flex: 0 1 2%;

        img {

          &#strelka {
          vertical-align: middle;
          margin: 0 auto;
        }

          &#find {
            padding: 0 7px;
            vertical-align: middle;
          }
      }

        &#menu {
          flex: 50% 1;
        }

        h3 {
          font: lighter 34px "Source Sans SemiBold";
          margin: 0px;
          color: black;
        }
      }
    }
  }

  nav {


    div {

      margin: 12px;
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


  main {
    flex: 1 0 auto;
    text-align: center;
    padding: 1em;
    min-height: 29.2em;
    max-width: 290px;
    margin: 0 auto;

    h2 {
      text-transform: uppercase;
      font-size: 3em;
      font-weight: 100;
    }
  }

  footer {
    flex: 0 0 auto;
    bottom: 0;
    font-size: medium;
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
        font-size: 26px;

        :hover {
          transition: 200ms;
          color: #249bd7;
          font-size: 30px;
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

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
