<template>
  <div id="top" class="page-container md-layout-column">
    <md-toolbar class="md-primary">
      <md-button class="md-icon-button" @click="showNavigation = true">
        <md-icon>menu</md-icon>
      </md-button>

      <span class="md-title">Meta Data</span>

      <div class="md-toolbar-section-end">
        <md-menu md-direction="bottom-start">
          <md-button class="md-icon-button" md-menu-trigger>
            <md-icon>contacts</md-icon>
          </md-button>

          <md-menu-content>
            <md-menu-item>
              <md-icon>thumb_up</md-icon>
              Do stuff
            </md-menu-item>
            <md-menu-item>
              <md-icon>home</md-icon>
              More things
            </md-menu-item>
            <md-menu-item>
              <md-icon>verified_user</md-icon>
              Thats the lot
            </md-menu-item>
          </md-menu-content>
        </md-menu>


        <md-button class="md-icon-button" @click="showSidepanel = true">
          <md-icon>favorite</md-icon>
        </md-button>
      </div>
    </md-toolbar>

    <!-- LEFT NAV -->
    <md-drawer name="d2" :md-active.sync="showNavigation">
      <md-toolbar class="md-transparent" md-elevation="0">
        <span class="md-title">Oceanids C2</span>
      </md-toolbar>

      <md-list>
        <md-list-item @click="movetoinbox()">
          <md-icon>move_to_inbox</md-icon>
          <span class="md-list-item-text">Inbox</span>
        </md-list-item>

        <md-list-item>
          <md-icon>send</md-icon>
          <span class="md-list-item-text" @click="first = true">Sent Mail</span>
        </md-list-item>

        <md-list-item>
          <md-icon>delete</md-icon>
          <span class="md-list-item-text" @click="second = true">Trash</span>
        </md-list-item>

        <md-list-item>
          <md-icon>error</md-icon>
          <span class="md-list-item-text">Spam</span>
        </md-list-item>
      </md-list>
    </md-drawer>

    <!-- RIGHT NAV -->
    <md-drawer name="d1" class="md-right" :md-active.sync="showSidepanel">
      <md-toolbar class="md-transparent" md-elevation="0">
        <span class="md-title">Favorites</span>
      </md-toolbar>

      <md-list>
        <md-list-item>
          <span class="md-list-item-text">Abbey Christansen</span>

          <md-button class="md-icon-button md-list-action">
            <md-icon class="md-primary">chat_bubble</md-icon>
          </md-button>
        </md-list-item>

        <md-list-item>
          <span class="md-list-item-text">Alex Nelson</span>

          <md-button class="md-icon-button md-list-action">
            <md-icon class="md-primary">chat_bubble</md-icon>
          </md-button>
        </md-list-item>

        <md-list-item>
          <span class="md-list-item-text">Mary Johnson</span>

          <md-button class="md-icon-button md-list-action">
            <md-icon>chat_bubble</md-icon>
          </md-button>
        </md-list-item>
      </md-list>
    </md-drawer>

    <md-content>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Error quibusdam, non molestias et! Earum magnam,
      similique, quo recusandae placeat dicta asperiores modi sint ea repudiandae maxime? Quae non explicabo, neque.
    </md-content>

    <div class="md-layout md-gutter md-alignment-center">
      <div class="md-layout-item md-medium-size-33 md-small-size-50 md-xsmall-size-100">
        <span>Always Show</span>
        <span>hahaha</span>
        <span>hohohohehe</span>
      </div>

      <div class="md-layout-item md-medium-size-33 md-small-size-50 md-xsmall-size-100">
        <span>Always Show</span>
      </div>

      <div class="md-layout-item md-medium-size-33 md-small-size-50 md-xsmall-size-100">
        <span>Always Show</span>
      </div>

      <div class="md-layout-item md-medium-size-50 md-small-size-50 md-xsmall-hide">
        <span>Hide Xsmall</span>
      </div>

      <div class="md-layout-item md-medium-size-50 md-small-hide">
        <span>Hide Small</span>
      </div>

      <div class="md-layout-item md-medium-hide">
        <span>Hide Medium</span>
      </div>
    </div>

    <div>
      <md-tabs class="md-primary" md-alignment="centered">
        <md-tab id="tab-home" md-label="Home">
          Lorem ipsum dolorit sequesturm bogitum psum dolorit sequesturm bogitupsum dolorit sequesturm
          bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum
          dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit
          sequesturm bogitupsum dolorit sequesturm bogitu

        </md-tab>
        <md-tab id="tab-pages" md-label="Pages">

          Lorem ipsum dolorit sequesturm bogitum psum dolorit sequesturm bogitupsum dolorit sequesturm
          bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum
          dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit
          sequesturm bogitupsum dolorit sequesturm bogitu Lorem ipsum dolorit sequesturm bogitum psum dolorit sequesturm bogitupsum dolorit sequesturm
          bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum
          dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit
          sequesturm bogitupsum dolorit sequesturm bogitu Lorem ipsum dolorit sequesturm bogitum psum dolorit sequesturm bogitupsum dolorit sequesturm
          bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum
          dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit
          sequesturm bogitupsum dolorit sequesturm bogitu

        </md-tab>
        <md-tab id="tab-posts" md-label="Posts">
          sturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit
          sequesturm bogitupsum dolorit sequesturm bogitu Lorem ipsum dolorit sequesturm bogitum psum dolorit sequesturm bogitupsum dolorit sequesturm
          bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum
          dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit
          sequesturm bogitupsum dolorit s
        </md-tab>
        <md-tab id="tab-favorites" md-label="Favorites">
          orit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit
          sequesturm bogitupsum dolorit sequesturm bogitu Lorem ipsum dolorit sequesturm bogitum psum dolorit sequesturm bogitupsum dolorit sequesturm
          bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum
          dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit
          sequesturm bogitupsum dolorit sequesturm bogitu Lorem ipsum dolorit sequesturm bogitum psum dolorit sequesturm bogitupsum dolorit sequesturm
          bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum
          dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit
          sequesturm bogitupsum dolorit seq
        </md-tab>
      </md-tabs>


    </div>

    <div class="phone-viewport">
      <md-bottom-bar md-type="shift">
        <md-bottom-bar-item id="bottom-bar-item-home" md-label="Home" md-icon="home"></md-bottom-bar-item>
        <md-bottom-bar-item id="bottom-bar-item-pages" md-label="Pages" md-icon="pages"></md-bottom-bar-item>
        <md-bottom-bar-item id="bottom-bar-item-posts" md-label="Posts"
                            md-icon="add"></md-bottom-bar-item>
        <md-bottom-bar-item id="bottom-bar-item-favorites" md-label="Favorites" md-icon="favorite"></md-bottom-bar-item>
      </md-bottom-bar>
    </div>

    <div>
      <md-dialog-alert
        :md-active.sync="first"
        md-content="Item has now been Created - let us rejoice !!"
        md-confirm-text="Fab !"/>

      <md-dialog-alert
        :md-active.sync="second"
        md-title="Item Deleted"
        md-content="Your item has been <b>DELETED</b> for now..."/>

    </div>

  </div>

</template>

<script>
  export default {
    name: 'Sidenav',
    data: () => ({
      showNavigation: false,
      showSidepanel: false,
      first: false,
      second: false
    }),
    methods: {
      movetoinbox () {
        this.showNavigation = false
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import '~vue-material/dist/theme/engine';

  .page-container {
    min-height: 300px;
    overflow: hidden;
    position: relative;
    border: 1px solid rgba(#000, .12);
  }

  // Demo purposes only
  .md-drawer {
    width: 230px;
    max-width: calc(100vw - 125px);
  }

  .md-content {
    padding: 16px;
  }

  .md-layout-item {
    height: 180px;
    margin-top: 8px;
    margin-bottom: 8px;


    span {
      width: 100%;
      height: 30%;
      padding: 8px;
      display: block;
      background: md-get-palette-color(teal, 200);
      border: 1px dashed darkorchid;
    }
  }

</style>
