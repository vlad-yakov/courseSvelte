<header>
   <button>
      <h2>SVET</h2>
   </button>
   <p>журнал об искусстве СНГ</p>
   <button>
      <img src="../search.png" width="35" height="35"/>
   </button>
</header>

<nav>
  <a href="ros.svelte">Россия</a>
  <a href="bel.svelte">Беларусь</a>
  <a href="ukr.svelte">Украина</a>
  <a href="kvz.svelte">Закавказье</a>
  <a href="as.svelte">Средняя Азия</a>
</nav>

<main>
	<h2>Привет.</h2>
	<p></p>
</main>

<footer>
   <div>
      <p>
         &#169; Яковлев Владислав
      </p>
   </div>
   <div class="social vk">
      <a href="https://vk.com/vlad_yakovlev28" target="_blank"><i class="fab fa-vk"></i></a>
   </div>

</footer>

<script>

</script>

<style lang='scss'>

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
       align-self: flex-end
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
       transition: all .3s cubic-bezier(.2, 0, 0, 1);
       z-index: 1;
    }
       :after {
           content: '';
           display: block;
           height: 0px;
           position: absolute;
           bottom: 0;
           right: 1.25rem;
           left: 1.25rem;
           background-color: #ffffff;
           transition: all .3s cubic-bezier(.2, 0, 0, 1);
           transform-origin: bottom center;
           z-index: -1;
         }

       nav a:hover {
           color: #2D2D2D;
       }

       nav a:hover:after {
           right: 0;
           left: 0;
           height: 100%;
       }

	main {
		text-align: center;
		padding: 1em;
		min-height: 29.2em;
		max-width: 290px;
		margin: 0 auto;
	}

	main h2 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 3em;
		font-weight: 100;
	}

	button {
	    background: rgba(255, 62, 0, 0);
	    border: none;
	    margin: 0
	}

	button:hover {
	background: rgba(255, 62, 0, 0.8);
	   transition: background 400ms;
	   border-radius: 0
	}

    footer {
    display: flex;
    color: black;
    height: 7em;
    background: #ff6533;
    }

   @import url(https://use.fontawesome.com/b36546ef62.css);
   .social a {
       text-align: center;
       width: 34px;
       height: 34px;
       float: left;
       background: #fff;
       box-shadow: 0 2px 4px rgba(0,0,0,0.15), inset 0 0 50px rgba(0,0,0,0.1);
       border-radius: 17px;
       margin: 10px;
       padding: 6px;
       color: #000;
   }

   .vk a:hover {
   background: #5d84ae;
   color: #fff}

   @media (min-width: 640px) {
	   main {
	      max-width: none;
	   }
   }

</style>