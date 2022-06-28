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
                <Header>Мария Святогор</Header>
                <AcdContent>
                    <div class="card-display">
                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/photo/wetransfer.jpg" alt="'Molchat Doma' для презентации"/>
                                </div>
                                <p class="spec">"'Molchat Doma' для презентации"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/photo/kurasov.jpeg" alt="Курасовщина, моя любовь"/>
                                </div>
                                <p class="spec">"Курасовщина, моя любовь"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/photo/bio.jpg" alt="Автобиография без фактов"/>
                                </div>
                                <p class="spec">"Автобиография без фактов"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/photo/Train-web.gif" alt="Автобиография без фактов"/>
                                </div>
                                <p class="spec">"Автобиография без фактов"</p>
                            </Card>
                        </div>
                    </div>
                </AcdContent>
            </Panel>

            <Panel>
                <Header>Андрей Ленкевич</Header>
                <AcdContent>
                    <div class="card-display">
                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/process.jpeg" alt=""/>
                                </div>
                                <p class="spec">"Коллаж 'Процессы Беларуси'"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/eye.jpeg" alt="Глядя в глаза пресвятого"/>
                                </div>
                                <p class="spec">"Глядя в глаза пресвятого"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/Pagan.jpg" alt="Язычники"/>
                                </div>
                                <p class="spec">"Язычники"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/mland.jpg" alt="До свидания, Родина"/>
                                </div>
                                <p class="spec">"До свидания, Родина"</p>
                            </Card>
                        </div>
                    </div>
                </AcdContent>
            </Panel>

            <Panel>
                <Header>Максим Сарычев</Header>
                <AcdContent>
                    <div class="card-display">
                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/2paws.jpeg" alt="Коллаж 'Друзья с двумя лапами'"/>
                                </div>
                                <p class="spec">"Бульдозер"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/gener.jpeg" alt="Голоса поколения Д"/>
                                </div>
                                <p class="spec">"Голоса поколения Д"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/found.jpg" alt="404: Not Found"/>
                                </div>
                                <p class="spec">"404: Not Found"</p>
                            </Card>
                        </div>

                        <div class="card-container" use:Ripple={{ surface: true, color: 'primary' }} tabindex="0">
                            <Card variant="outlined">
                                <div class="canv">
                                    <img src="build/img/bel/arms.jpg" alt="Привет оружию"/>
                                </div>
                                <p class="spec">"Привет оружию"</p>
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
            //name: 'Дмитрий Марков',
            ['build/img/rus/photo/market.jpg', 'Дмитрий Марков', '"В каждом поселковом магазине должен быть кот"'],
            ['build/img/rus/photo/kringe.jpg', 'Дмитрий Марков', '"Дедушка с книжкой"'],
            ['build/img/rus/photo/poly.jpg', 'Дмитрий Марков', '"Столько деталей в одном кадре"'],
            ['build/img/rus/photo/kontrast.jpg', 'Дмитрий Марков', '"Контрасты"'],
        ],

        [
            //name: 'Яна Романова',
            ['build/img/rus/photo/exo.jpg', 'Яна Романова', '"Экзотариум"'],
            ['build/img/rus/photo/welsh.png', 'Яна Романова', '"Притяние Уэльса"', '2015-2016'],
            ['build/img/rus/photo/shvili.jpg', 'Яна Романова', '"Швилишвили"'],
            ['build/img/rus/photo/immerse.jpg', 'Яна Романова', '"Погружение"', '2014'],
        ],

        [
            //name: 'Александр Петросян',
            ['build/img/rus/photo/animals.jpg', 'Александр Петросян', '"Пёс и кот"'],
            ['build/img/rus/photo/bus.png', 'Александр Петросян', '"В маршрутке"'],
            ['build/img/rus/photo/dinner.jpg', 'Александр Петросян', '"Больничный обед"'],
            ['build/img/rus/photo/feast.jpg', 'Александр Петросян', '"После праздника"'],
        ],
    ];

    let ukr = [
        [
            //name: 'Арсен Савадов',
            ['build/img/ukr/photo/relation.jpg', 'Арсен Савадов', '"Любовная история"', '2000'],
            ['build/img/ukr/photo/don.jpg', 'Арсен Савадов', '"Донбасс-шоколад"', '1997'],
            ['build/img/ukr/photo/sad.jpg', 'Арсен Савадов', '"Марксизм де сад"'],
            ['build/img/ukr/photo/kokto.jpg', 'Арсен Савадов', '"Kokto"', '2001'],
        ],

        [
            //name: 'Сергей Братков',
            ['build/img/ukr/photo/lukom.webp', 'Сергей Братков', '"Лукоморье"', '2015'],
            ['build/img/ukr/photo/isabel.webp', 'Сергей Братков', '"Изабелла"', '2016'],
            ['build/img/ukr/photo/zagovor.jpg', 'Сергей Братков', 'Из серии "Заговор"', '2014'],
            ['build/img/ukr/photo/nowar.webp', 'Сергей Братков', '"Ни войны, ни мира"', '2011'],
        ],

        [
            //name: 'Михаил Палинчак',
            ['build/img/ukr/photo/blur.jpg', 'Михаил Палинчак', '"Размытый"', '2016'],
            ['build/img/ukr/photo/shirok.jpg', 'Михаил Палинчак', '"Широкино"', '2016'],
            ['build/img/ukr/photo/covid.jpg', 'Михаил Палинчак', '"Анамнесис"', '2020'],
            ['build/img/ukr/photo/salt.jpg', 'Михаил Палинчак', '"Соль"', '2015'],
        ],

        [
            //name: 'Игорь Чекачков',
            ['build/img/ukr/photo/sleep.jpg', 'Игорь Чекачков', '"Сон"']
            ['build/img/ukr/photo/Obscur.jpg', 'Игорь Чекачков', '"Неизвестная земля"'],
            ['build/img/ukr/photo/destroy.jpg', 'Игорь Чекачков', '"NA4JOPM8 "'],
            ['build/img/ukr/photo/daily.jpg', 'Игорь Чекачков', '"Повседневная жизнь переселённых лиц"'],
        ],
    ];

    let bel = [
        [
            //name: 'Мария Святогор'
            ['build/img/bel/photo/wetransfer.jpg', 'Мария Святогор', '"Molchat Doma" для презентации','2020'],
            ['build/img/bel/photo/kurasov.jpeg', 'Мария Святогор', '"Курасовщина, моя любовь"', '2015-2017'],
            ['build/img/bel/photo/bio.jpg', 'Мария Святогор', '"Автобиография без фактов"', '2016-2022'],
            ['build/img/bel/photo/Train-web.gif', 'Мария Святогор', '"Автобиография без фактов".', '2016-2022'],
        ],

        [
            //name: 'Андрей Ленкевич'
            ['build/img/bel/process.jpeg', 'Андрей Ленкевич', 'Коллаж "Процессы Беларуси"', '2020-2021'],
            ['build/img/bel/eye.jpeg', 'Андрей Ленкевич', '"Глядя в глаза пресвятого"', '2011'],
            ['build/img/bel/Pagan.jpg', 'Андрей Ленкевич', '"Язычники"', '2008-2010'],
            ['build/img/bel/mland.jpg', 'Андрей Ленкевич', '"До свидания, Родина".', '2011'],
        ],

        [
            //name: 'Максим Сарычев'
            ['build/img/bel/2paws.jpeg', 'Максим Сарычев', 'Коллаж "Друзья с двумя лапами"', '2013'],
            ['build/img/bel/gener.jpeg', 'Максим Сарычев', '"Голоса поколения Д"'],
            ['build/img/bel/found.jpg', 'Максим Сарычев', '"404: Not Found"', '2015'],
            ['build/img/bel/arms.jpg', 'Максим Сарычев', '"Привет оружию".', '2012-2015'],
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
