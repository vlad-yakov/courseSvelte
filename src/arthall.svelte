<div class="tbody">
    <hr/>
    <TabBar tabs={['Беларусь', 'Украина', 'Россия']} let:tab bind:active on:click={() => ( window.$('button.mdc-tab.mdc-tab--active.mdc-ripple-upgraded .mdc-ripple-upgraded--background-focused').removeClass('mdc-ripple-upgraded--background-focused'))}>
        <Tab {tab} >
            <Label>{tab}</Label>
        </Tab>
    </TabBar>

    <div class="card-display">
        <div class="card-container">
            <Card padded>A simple padded card.</Card>
        </div>

        <div class="card-container">
            <Card>
                <Content>You can also use <code>Content</code>.</Content>
            </Card>
        </div>

        <div class="card-container">
            <Card variant="outlined" padded>An outlined, padded card.</Card>
        </div>
    </div>
</div>
<script>
    import Tab, { Label } from '@smui/tab';
    import TabBar from '@smui/tab-bar';

    import Card, { Content } from '@smui/card';

    let active = 'Беларусь';

</script>

<style lang="scss">

  .tbody {
    hr {
      margin: 0;
    }
  }

</style>