<template>
  <div id="top" class="page-container md-layout-column">


    <!-- TOOLBAR -->
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

    <!-- TAB BAR -->
    <div>
      <md-tabs class="md-primary" md-alignment="left">
        <md-tab id="tab-home" md-label="Projects">
          Lorem ipsum dolorit sequesturm bogitum psum dolorit sequesturm bogitupsum dolorit sequesturm

        </md-tab>
        <md-tab id="tab-pages" md-label="Campaigns">

          Lorem ipsum dolorit sequesturm bogitum psum dolorit sequesturm bogitupsum dolorit sequesturm
          bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum


        </md-tab>
        <md-tab id="tab-posts" md-label="Vehicles">
          sturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit
          sequesturm bogitupsum dolorit s
        </md-tab>
        <md-tab id="tab-favorites" md-label="Sensors">
          psum dolorit sequesturm
          bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum
          dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit sequesturm bogitupsum dolorit
          sequesturm bogitupsum dolorit seq
        </md-tab>
      </md-tabs>


    </div>

    <!-- MAIN FORM AND OR CARD CONTENT -->



    <div class="md-layout md-gutter md-alignment-top-center">


      <div class="md-layout-item md-medium-size-50 md-small-size-50 md-xsmall-size-100">
        <span>Project editing form</span>
        <md-card md-with-hover>
          <md-ripple>
            <md-card-header class="md-accent">
              <div class="md-title">Add a new Project</div>
              <div class="md-subhead">Projects contain campaigns</div>
            </md-card-header>

            <md-card-content>

              <!-- Form elements here -->
              <div>
                <md-field md-clearable>
                  <label>Name</label>
                  <md-input md-counter="30"></md-input>
                </md-field>

                <md-field>
                  <label>Principle Investigator</label>
                  <md-select name="piuser" id="piuser">
                    <md-option value="1">Akabaka MacKaka</md-option>
                    <md-option value="2">Mary McTavish</md-option>
                    <md-option value="3">Joe Bloggs</md-option>
                  </md-select>
                </md-field>

                <md-field>
                  <label>Description</label>
                  <md-textarea required></md-textarea>
                  <i class="md-helper-text">Enter lots of information</i>
                </md-field>


                <md-field md-clearable>
                  <md-icon class="md-primary">link</md-icon>
                  <label>Project site URL</label>
                  <md-input md-counter="40"></md-input>
                </md-field>

                <md-field>
                  <label>Upload project logo</label>
                  <md-file placeholder="Upload project logo" />
                </md-field>

                <md-checkbox v-model="publicproject" class="md-primary">Public</md-checkbox>

              </div>

              <md-speed-dial class="md-bottom-right" md-direction="top">
                <md-speed-dial-target>
                  <md-icon class="md-morph-initial">add</md-icon>
                  <md-icon class="md-morph-final">edit</md-icon>
                </md-speed-dial-target>

                <md-speed-dial-content>
                  <md-button class="md-icon-button">
                    <md-icon>note</md-icon>
                  </md-button>

                  <md-button class="md-icon-button">
                    <md-icon>event</md-icon>
                  </md-button>
                </md-speed-dial-content>
              </md-speed-dial>

            </md-card-content>

            <md-card-actions md-alignment="left">
              <md-button class="md-raised md-primary">Create Project</md-button>
              <md-button class="md-raised md-accent">Cancel</md-button>
            </md-card-actions>
          </md-ripple>


        </md-card>

      </div>




      <div class="md-layout-item md-medium-size-50 md-small-size-50 md-xsmall-size-100">
        <span>Always Show</span>

        <md-card md-with-hover>
          <md-ripple>
            <md-card-header>
              <div class="md-title">Card with hover effect</div>
              <div class="md-subhead">It also have a ripple</div>
            </md-card-header>

            <md-card-content>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non.
            </md-card-content>

            <md-card-actions>
              <md-button class="md-primary">Action-1</md-button>
              <md-button class="md-accent">Action-2</md-button>
            </md-card-actions>
          </md-ripple>
        </md-card>
      </div>

</div>

<!--
      <div class="md-layout-item md-medium-size-25 md-small-size-50 md-xsmall-size-100">
        <span>Always Show</span>

        <md-card md-with-hover>
          <md-ripple>
            <md-card-header>
              <div class="md-title">Card with hover effect</div>
              <div class="md-subhead">It also have a ripple</div>
            </md-card-header>

            <md-card-content>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non.
            </md-card-content>

            <md-card-actions>
              <md-button class="md-primary">Action-1</md-button>
              <md-button class="md-accent">Action-2</md-button>
            </md-card-actions>
          </md-ripple>
        </md-card>

      </div>

      <div class="md-layout-item md-medium-size-25 md-small-size-50 md-xsmall-size-100">
        <span>Always Show</span>
        <md-card md-with-hover>
          <md-ripple>
            <md-card-header>
              <div class="md-title">Card with hover effect</div>
              <div class="md-subhead">It also have a ripple</div>
            </md-card-header>

            <md-card-content>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non.
            </md-card-content>

            <md-card-actions>
              <md-button class="md-primary">Action-1</md-button>
              <md-button class="md-accent">Action-2</md-button>
            </md-card-actions>
          </md-ripple>
        </md-card>
      </div>

      <div class="md-layout-item md-medium-size-25 md-small-size-50 md-xsmall-hide">
        <span>Hide Xsmall</span>
        <md-card md-with-hover>
          <md-ripple>
            <md-card-header>
              <div class="md-title">Card with hover effect</div>
              <div class="md-subhead">It also have a ripple</div>
            </md-card-header>

            <md-card-content>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non.
            </md-card-content>

            <md-card-actions>
              <md-button class="md-primary">Action-1</md-button>
              <md-button class="md-accent">Action-2</md-button>
            </md-card-actions>
          </md-ripple>
        </md-card>
      </div>

      <div class="md-layout-item md-medium-size-25 md-small-hide">
        <span>Hide Small</span>
        <md-card md-with-hover>
          <md-ripple>
            <md-card-header>
              <div class="md-title">Card with hover effect</div>
              <div class="md-subhead">It also have a ripple</div>
            </md-card-header>

            <md-card-content>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non.
            </md-card-content>

            <md-card-actions>
              <md-button class="md-primary">Action-1</md-button>
              <md-button class="md-accent">Action-2</md-button>
            </md-card-actions>
          </md-ripple>
        </md-card>
      </div>


      <div class="md-layout-item md-medium-hide  md-large-size-33">
        <span>Hide Medium</span>
        <md-card md-with-hover class="md-layout-item md-medium-hide  md-large-size-33">
          <md-ripple>
            <md-card-header>
              <div class="md-title">Card with hover effect</div>
              <div class="md-subhead">It also have a ripple</div>
            </md-card-header>

            <md-card-content>

              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non.
            </md-card-content>

            <md-card-actions>
              <md-button class="md-primary">Action-1</md-button>
              <md-button class="md-accent">Action-2</md-button>
            </md-card-actions>
          </md-ripple>
        </md-card>
      </div>

      <div class="md-layout-item md-medium-hide  md-large-size-33">
        <span>Hide Medium</span>
        <md-card md-with-hover>
          <md-ripple>
            <md-card-header>
              <div class="md-title">Card with hover effect</div>
              <div class="md-subhead">It also have a ripple</div>
            </md-card-header>

            <md-card-content>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non.
            </md-card-content>

            <md-card-actions>
              <md-button class="md-primary">Action-1</md-button>
              <md-button class="md-accent">Action-2</md-button>
            </md-card-actions>
          </md-ripple>
        </md-card>
      </div>

      <div class="md-layout-item md-medium-hide  md-large-size-33">
        <span>Hide Medium</span>
        <md-card md-with-hover>
          <md-ripple>
            <md-card-header>
              <div class="md-title">Card with hover effect</div>
              <div class="md-subhead">It also have a ripple</div>
            </md-card-header>

            <md-card-content>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non.
            </md-card-content>

            <md-card-actions>
              <md-button class="md-primary">Action-1</md-button>
              <md-button class="md-accent">Action-2</md-button>
            </md-card-actions>
          </md-ripple>
        </md-card>
      </div>


    </div>

    -->


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
        md-confirm-text="Spiffing !"/>

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
      second: false,
      publicproject: false
    }),
    methods: {
      movetoinbox() {
        this.showNavigation = false
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import '~vue-material/dist/theme/engine';

  .page-container {
    min-height: 600px;
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
    min-height: 180px;
    margin-top: 8px;
    margin-bottom: 8px;

    span {
      width: 100%;
      height: 30%;
      padding: 8px;
      display: block;
      background: md-get-palette-color(teal, 200);

    }
  }


</style>
