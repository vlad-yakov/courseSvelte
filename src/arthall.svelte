<div class="tbody">
    <hr/>
    <TabBar tabs={['Беларусь', 'Украина', 'Россия']} let:tab bind:active on:click={() => ( window.$('button.mdc-tab.mdc-tab--active.mdc-ripple-upgraded .mdc-ripple-upgraded--background-focused').removeClass('mdc-ripple-upgraded--background-focused'))}>
        <Tab {tab} >
            <Label>{tab}</Label>

        </Tab>
    </TabBar>

    <div class="card-display">
        <div class="card-container">
            <Card>
                <Media class="card-media-16x9" aspectRatio="16x9">
                    <MediaContent>
                        <h2
                                class="mdc-typography--headline6"
                                style="color: #fff; position: absolute; bottom: 16px; left: 16px; margin: 0;"
                        >
                            A card with 16x9 media.
                        </h2>
                    </MediaContent>
                </Media>
                <Content style="color: #888;">Here's some gray text down here.</Content>
            </Card>
        </div>

        <div class="card-container">
            <Card style="min-width: 300px;">
                <Media class="card-media-square" aspectRatio="square">
                    <div style="color: #fff; position: absolute; bottom: 16px; left: 16px;">
                        <h2 class="mdc-typography--headline6" style="margin: 0;">
                            A card with square media.
                        </h2>
                        <h3 class="mdc-typography--subtitle2" style="margin: 0;">
                            And a subtitle.
                        </h3>
                    </div>
                </Media>
            </Card>
        </div>

        <div class="card-container">
            <Card>
                <div style="padding: 1rem;">
                    <h2 class="mdc-typography--headline6" style="margin: 0;">
                        A card with media.
                    </h2>
                    <h3 class="mdc-typography--subtitle2" style="margin: 0; color: #888;">
                        And a subtitle.
                    </h3>
                </div>

                    <Media class="card-media-16x9" aspectRatio="16x9" />
                    <Content class="mdc-typography--body2">
                        And some info text. And the media and info text are a primary action
                        for the card.
                    </Content>

            </Card>
        </div>
    </div>
</div>

<script>
    import Tab, { Label } from '@smui/tab';
    import TabBar from '@smui/tab-bar';

    import Card, {
        Content,
        PrimaryAction,
        Media,
        MediaContent,
    } from '@smui/card';

    let active = 'Беларусь';

</script>

<style lang="scss">

  .tbody {
    hr {
      margin: 0;
    }
    * :global(.card-media-16x9) {
      background-image: url(https://place-hold.it/320x180?text=16x9&fontsize=23);
    }

    * :global(.card-media-square) {
      background-image: url(https://place-hold.it/320x320?text=square&fontsize=23);
    }
  }

</style>