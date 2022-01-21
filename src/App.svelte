
<header>
  <button>
    <h2>колорит</h2>
  </button>
  <button>
    <img src="../search.png" width="35" height="35" alt="поиск" />
  </button>
</header>

<nav>
  <a href="ros.svelte">Россия</a>
  <a href="bel.svelte">Беларусь</a>
  <a href="ukr.svelte">Украина</a>
  <a href="kvz.svelte">Закавказье</a>
  <a href="as.svelte">Средняя Азия</a>
</nav>

<!--журнал будет называться молния-->
<main>
  <h2>Привет.</h2>
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
</main>

<footer>
 <div>
   <h3>
     колорит
   </h3>
   <p>
     культжурнал про искусство в СНГ
   </p>
   <p>
     &#169 2022
   </p>
 </div>
  <div>
  </div>
  <div class="social vk">
    <a href="https://vk.com/vlad_yakovlev28" target="_blank"
      ><i class="fa fa-vk" aria-hidden="true" /></a
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
</footer>

<style lang="scss">
  header {
    display: flex;
    justify-content: space-between;
    line-height: 35px;
  }

  header h2 {
    margin: 0.15em;
    font-size: 2.5em;
    font-weight: 100;
  }

  header p {
    flex-grow: 2;
    margin: 13px 5px;
    white-space: nowrap;
    align-self: flex-end;
  }

  nav {
    height: 9vh;
    background: rgb(255, 62, 0, 0.8);
    display: flex;
    justify-content: space-around;
  }

  nav a {
    display: block;
    padding: 1rem 1.25rem;
    font-size: 1.2rem;
    text-decoration: none;
    color: white;
    position: relative;
    transition: all 0.3s cubic-bezier(0.2, 0, 0, 1);
    z-index: 1;

    &:after {
      content: "";
      display: block;
      height: 0px;
      position: absolute;
      bottom: 0;
      right: 1.25rem;
      left: 1.25rem;
      background-color: #ffffff;
      transition: all 0.3s cubic-bezier(0.2, 0, 0, 1);
      transform-origin: bottom center;
      z-index: -1;
    }
  }

  nav a:hover {
    color: #2d2d2d;

    &:after {
      right: 0;
      left: 0;
      height: 100%;
    }
  }

  main {
    text-align: center;
    padding: 1em;
    min-height: 29.2em;
    max-width: 290px;
    margin: 0 auto;

    h2 {
      color: #ff3e00;
      text-transform: uppercase;
      font-size: 3em;
      font-weight: 100;
    }
  }

  button {
    background: rgba(255, 62, 0, 0);
    border: none;
    margin: 0;
  }

  button:hover {
    background: rgba(255, 62, 0, 0.8);
    transition: background 400ms;
    border-radius: 0;
  }

  footer {
    display: flex;
    color: black;
    height: 7em;
    background: #ff6533;
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
    color: #fff;
    transition: 250ms;
  }

  .tg a {
    font-size: 25px;
  }

  .vk a:hover {
    font-size: 220%;
    transition: 250ms;
    color: #5d84ae;
  }

  .tg a:hover {
    font-size: 205%;
    transition: 250ms;
    transition: 250ms;
    color: #249bd7;
  }

  .pinterest a:hover {
    font-size: 220%;
    transition: 250ms;
    transition: 250ms;
    color: #c8232c;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
