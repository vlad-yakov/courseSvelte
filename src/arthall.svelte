<Dialog bind:open>
    <Content id="fullscreen-content">
        <Button><Label>{a_alt}</Label></Button>
    </Content>
</Dialog>

<div class="tbody">
    <hr/>
    <TabBar tabs={[state[0], state[1], state[2]]} let:tab bind:active on:click={() => ( window.$('button.mdc-tab.mdc-tab--active.mdc-ripple-upgraded .mdc-ripple-upgraded--background-focused').removeClass('mdc-ripple-upgraded--background-focused'))}>
        <Tab {tab} >
            <Label>{tab}</Label>
        </Tab>
    </TabBar>

    <div class="accordion-container">
        <Accordion multiple>
            <Panel>
                <Header>Захар Кудин</Header>
                <AcdContent>
                    <div class="card-display">
                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/machine.jpeg" alt="Бульдозер"/>
                                </div>
                                <p class="spec">"Бульдозер"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/present.jpeg" alt="Портрет современника"/>
                                </div>
                                <p class="spec">"Портрет современника"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/houses.jpg" alt="Я делаю Беларусь?"/>
                                </div>
                                <p class="spec">"Я делаю Беларусь?"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/mural.jpg" alt="Ледяной полет. Горячий космос."/>
                                </div>
                                <p class="spec">"Ледяной полет. Горячий космос."</p>
                            </Card>
                        </div>
                    </div>
                </AcdContent>
            </Panel>

            <Panel>
                <Header>Виктор Сергей</Header>
                <AcdContent>
                    <div class="card-display">
                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/swimmer.png" alt="Пловец. Бумага, тушь. 2014"/>
                                </div>
                                <p class="spec">"Пловец"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/transform.png" alt="Трансформация"/>
                                </div>
                                <p class="spec">"Трансформация"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/style.jpg", alt="Стилизация"/>
                                </div>
                                <p class="spec">"Стилизация"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="null" alt=""/>
                                </div>
                                <p class="spec"></p>
                            </Card>
                        </div>
                    </div>
                </AcdContent>
            </Panel>

            <Panel>
                <Header>Жанна Гладко
                    </Header>
                <AcdContent>
                    <div class="card-display">
                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/piano.jpg" alt="'Луна лучится как латунь'. 2011-2019"/>
                                </div>
                                <p class="spec">"Луна лучится как латунь"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/moon.jpg" alt="Луна лучится как латунь. 2011-2019"/>
                                </div>
                                <p class="spec">"Луна лучится как латунь"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/240.jpg" alt="Луна лучится как латунь. 2011-2019"/>
                                </div>
                                <p class="spec">"Луна лучится как латунь"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/target.jpg" alt="Подстрекающая сила. 1997"/>
                                </div>
                                <p class="spec">""</p>
                            </Card>
                        </div>
                    </div>
                </AcdContent>
            </Panel>
        </Accordion>
    </div>

</div>
<script>
    import Tab, { Label } from '@smui/tab';
    import TabBar from '@smui/tab-bar';
    import Card from '@smui/card';

    import Ripple from '@smui/ripple';

    import Dialog, { Content } from '@smui/dialog';
    import Button from '@smui/button';

    import Accordion, { Panel, Header, Content as AcdContent } from '@smui-extra/accordion';

    let open = false;

    let state = [
        'Беларусь', 'Украина', 'Россия'
    ];

    let rus = [
        [
            //name: 'Илья и Эмилия Кабаковы',
            ['build/img/rus/street.jpg', 'Илья Кабаков', 'К книге "Откуда пришла улица?"', 'Иллюстрация. 1980'],
            ['build/img/rus/space.jpg', 'Илья Кабаков', '"Человек, улетевший в космос из своей комнаты"', 'Инсталляция. 1985'],
            ['build/img/rus/freedom.jpg', 'Илья и Эмилия Кабаковы', 'Из цикла "Четыре картины о свободе"', 'Графика. 2012'],
            ['build/img/rus/book.jpg', 'Илья Кабаков', 'Из Мурзилки "Мастерами делаются"', 'Иллюстрация. 1988'],
        ],

        [
            //name: 'Эрик Булатов',
            ['build/img/rus/sign.jpg', 'Эрик Булатов', '"Дорожный знак"', 'Карандаши. 1990'],
            ['build/img/rus/mocart.jpg', 'Эрик Булатов', '"Моцарт". Холст', 'Масло. 1991'],
            ['build/img/rus/jokonda.jpg', 'Эрик Булатов', '"Лувр. Джоконда."', 'Холст, масло. 2006'],
            [null, null, null, null],
        ],

        [
            //name: 'AES+F',
            ['build/img/rus/islam.jpg', 'AES+F', 'Из серии "Исламский проект". 1996-2003'],
            ['build/img/rus/suspect.jpg', 'AES+F', 'Серия "Подозреваемые". 1997'],
            ['build/img/rus/hlflv.jpg', 'AES+F', 'Из серии "Action Half-life". 2003-2005'],
            [null, null, null, null],
        ],
    ];

    let ukr = [
        [
            //name: 'Никита Кадан',
            ['build/img/ukr/cherevyk.jpg', 'Никита Кадан', 'Четырнадцатая в проекте "Процедурная комната"', '2009-2010'],
            ['build/img/ukr/dust.jpg', 'Никита Кадан', 'Четвёртая в проекте "Планы по пыли"', '2013'],
            ['build/img/ukr/stolpnik.jpg', 'Никита Кадан', '"Столпник (Занять место)"', 'Печать. 2015'],
            ['build/img/ukr/spec.jpg', 'Никита Кадан', '"Зрители"', 'Уголь. 2016'],
            //['build/img/ukr/plants.jpg','Никита Кадан', '"Защита растений".', 'Бумага, коллаж, 2014']
        ],

        [
            //name: 'Александра Кадзевич',
            ['build/img/ukr/peoples.jpg', 'Александра Кадзевич', '"Эксперт по времени воспроизведения"', '2020'],
            ['build/img/ukr/freelive.jpg', 'Александра Кадзевич', '"Освобождённое проживание"', '2018'],
            ['build/img/ukr/trumb.jpg', 'Александра Кадзевич', '"Жилой пейзаж с человеческой тенью"', '2020'],
            ['build/img/ukr/sekreter.jpg', 'Александра Кадзевич', '"Осётр, седой, секретарь"', '2019'],
        ],

        [
            //name: 'Анатолий Криволап',
            ['build/img/ukr/cows.jpg', 'Анатолий Криволап', 'Из серии "Медитативный пейзаж"', 'Холст, масло. 2014'],
            ['build/img/ukr/walk.jpg', 'Анатолий Криволап', '"Зимняя прогулка"', 'Полотно,масло. 2015'],
            ['build/img/ukr/canev.jpg', 'Анатолий Криволап', 'Из цикла "Каневские мотивы"', 'Холст, масло. 2011'],
            ['build/img/ukr/.jpg', 'Анатолий Криволап', '"Зеркало Украины"', 'Холст, масло. 2013'],
        ],
    ];

    let bel = [
        [
            //name: 'Захар Кудин'
            ['build/img/bel/machine.jpeg', 'Захар Кудин', '"Бульдозер"',],
            ['build/img/bel/present.jpeg', 'Захар Кудин', '"Портрет современника"',],
            ['build/img/bel/houses.jpg', 'Захар Кудин', '"Я делаю Беларусь?"',],
            ['build/img/bel/mural.jpg', 'Захар Кудин', '"Ледяной полет. Горячий космос"', 'Мурал'],
        ],

        [
            //name: 'Виктор Сергей'
            ['build/img/bel/swimmer.png', 'Виктор Сергей', '"Пловец"', 'Бумага, тушь. 2014'],
            ['build/img/bel/transform.png', 'Виктор Сергей', '"Трансформация"'],
            ['build/img/bel/style.jpg', 'Виктор Сергей', '"Стилизация"'],
            [null, null, null, null],
        ],
        [
            //name: 'Жанна Гладко'
            ['build/img/bel/piano.jpg', 'Жанна Гладко', '"Луна лучится как латунь"', '2011-2019'],
            ['build/img/bel/moon.jpg', 'Жанна Гладко', '"Луна лучится как латунь"', '2011-2019'],
            ['build/img/bel/240.jpg', 'Жанна Гладко', '"Луна лучится как латунь"', '2011-2019'],
            ['build/img/bel/target.jpg', 'Жанна Гладко', '"Подстрекающая сила"', '1997'],
        ],
    ];

    let active = bel[0];

    export let a_alt = "";

    window.$(function(){
        //вывод изображения в диалог
        window.$('.mdc-card').click(function(event) {
            open = true
            let a_path = window.$(this).find('img').attr('src');
            a_alt = window.$(this).find('img').attr('alt');
            window.$('#fullscreen-content').prepend('<div id="pict"><img src="'+a_path+'" style="max-width:1332px;max-height:620px;"></div>');
        });
        window.$('.mdc-dialog__scrim').click(function() {
            window.$('#pict').remove();
        });

        //добавление раздела-аккордеона
        window.$('.mdc-tab').mousedown(function(event) {
            if (event.currentTarget.childNodes[0].firstChild.textContent == 'Россия') {
                let i = 0;
                let j = 0;
                let nodtitle = window.$('.smui-accordion__header__title');
                for (let arti of rus) {
                    if (j>2) break;
                    nodtitle[j].innerHTML = arti[0][1];
                    ++j;
                    for(let p of arti) {
                        let nodimg = window.$('.canv')[i];
                        let nodp = window.$('.spec')[i];
                        if (p[0] == null) {
                            nodimg.parentNode.parentNode.remove()
                            continue;
                        }
                        nodimg.firstChild.setAttribute('src', p[0]);
                        nodp.innerHTML = p[2];
                        let desc = p.slice([1]);
                        nodimg.firstChild.setAttribute('alt', desc);
                        ++i;
                    }
                }
            } else if(event.currentTarget.childNodes[0].firstChild.textContent == 'Украина') {
                let i = 0;
                let j = 0;
                let nodtitle = window.$('.smui-accordion__header__title');
                for (let arti of ukr) {
                    if (j>2) break;
                    nodtitle[j].innerHTML = arti[0][1];
                    ++j;
                    for (let p of arti) {
                        let nodimg = window.$('.canv')[i];
                        let nodp = window.$('.spec')[i];
                        if (p[0] == null) {
                            nodimg.parentNode.parentNode.remove()
                            continue;
                        }
                        nodimg.firstChild.setAttribute('src', p[0]);
                        nodp.innerHTML = p[2];
                        let desc = p.slice([1]);
                        nodimg.firstChild.setAttribute('alt', desc);
                        ++i;
                    }
                }
            } else {
                let i = 0;
                let j = 0;
                let nodtitle = window.$('.smui-accordion__header__title');
                for (let arti of bel) {
                    if (j>2) break;
                    nodtitle[j].innerHTML = arti[0][1];
                    ++j;
                    for (let p of arti) {
                        let nodimg = window.$('.canv')[i];
                        let nodp = window.$('.spec')[i];
                        if (p[0] == null) {
                            nodimg.parentNode.parentNode.remove()
                            continue;
                        }
                        nodimg.firstChild.setAttribute('src', p[0]);
                        nodp.innerHTML = p[2];
                        let desc = p.slice([1]);
                        nodimg.firstChild.setAttribute('alt', desc);
                        ++i;
                    }
                }
            }
        });
    });
</script>

<style lang="scss">

  .tbody {
    hr {
      margin: 0;
    }

    .card-container {
      cursor: pointer;
      transition: 0.33s;

      &:hover {
        transform: scale(1.05);
      }

      div.canv {
        z-index: 9999;

        img {
          width: 260px;
          height: 150px;
        }
      }

      p.spec {
        width: 260px;
        font-size: 12px;
      }
    }
  }

</style>
