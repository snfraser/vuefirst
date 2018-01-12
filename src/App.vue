<template>
  <div id="top" class="page-container md-layout-column">

    <md-app>

      <!-- TOOLBAR -->
      <md-app-toolbar class="md-primary">
        <md-button class="md-icon-button" @click="showNavigation = true">
          <md-icon>menu</md-icon>
        </md-button>

        <span class="md-title">Pilot</span>
        <span class="md-title">Create</span>
        <span class="md-title">Explore</span>
        <span class="md-title">Admin</span>

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
            <md-icon>menu</md-icon>
          </md-button>
        </div>
      </md-app-toolbar>

      <!-- LEFT NAV -->
      <!-- SET MEDIA QUERY TO DECIDE ITS MD-PERMANENT STATUS -->
      <md-app-drawer name="d2" :md-active.sync="showNavigation" md-permanent="clipped">
        <md-toolbar class="md-transparent" md-elevation="0">
          <span class="md-title">Metadata</span>
        </md-toolbar>

        <md-list>
          <md-list-item md-expand>
            <md-icon>folder</md-icon>
            <span class="md-list-item-text">Projects</span>
            <md-list slot="md-expand">
              <md-list-item class="md-inset">Create</md-list-item>
              <md-list-item class="md-inset">Update</md-list-item>
              <md-list-item class="md-inset">View</md-list-item>
            </md-list>


            <md-select slot="md-expand">
              <md-option value="1">MASSMO</md-option>
              <md-option value="2">OSNAP</md-option>
              <md-option value="3">EEL</md-option>
              <md-option value="4">ALTERECO</md-option>
              <md-option value="5">BOBBLE</md-option>
              <md-option value="6">MERMEED</md-option>
            </md-select>


          </md-list-item>


          <md-list-item>
            <md-icon>language</md-icon>
            <span class="md-list-item-text" @click="first = true">Campaigns</span>
          </md-list-item>

          <md-list-item>
            <md-icon>toys</md-icon>
            <span class="md-list-item-text" @click="second = true">Deployments</span>
          </md-list-item>

          <md-list-item>
            <md-icon>local_airport</md-icon>
            <span class="md-list-item-text">Vehicles</span>
          </md-list-item>

          <md-list-item>
            <md-icon>wifi</md-icon>
            <span class="md-list-item-text">Sensors</span>
          </md-list-item>


        </md-list>
      </md-app-drawer>

      <!-- RIGHT NAV -->
      <!--
      <md-app-drawer name="d1" class="md-right" :md-active.sync="showSidepanel">
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
      </md-app-drawer>

      -->

      <md-app-content>
       <span>Content that goes above the forms here</span>
        <!-- TAB BAR -->
        <!--
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
        -->

        <!-- MAIN FORM AND OR CARD CONTENT -->

        <div class="md-layout md-gutter md-alignment-top-center">


          <div class="md-layout-item md-medium-size-50 md-small-size-50 md-xsmall-size-100">
            <span>Project editing form</span>
            <md-card md-with-hover>

                <md-card-header class="md-accent">
                  <div class="md-title">Add a new Project</div>
                  <div class="md-subhead">Projects contain campaigns</div>
                </md-card-header>

                <md-card-content>

                  <!-- Form elements here -->
                  <div>
                    <md-field md-clearable>
                      <label>Name</label>
                      <md-input md-counter="30" v-model="form.name"></md-input>
                    </md-field>

                    <md-field>
                      <label>Principle Investigator</label>
                      <md-select name="piuser" v-model="form.pi">
                        <md-option v-for="(u, index) in users" :value="u.id" :key="index">{{u.name}}</md-option>
                      </md-select>
                    </md-field>

                    <md-field>
                      <label>Description</label>
                      <md-textarea required v-model="form.desc"></md-textarea>
                      <i class="md-helper-text">Enter lots of information</i>
                    </md-field>


                    <md-field md-clearable >
                      <md-icon class="md-primary">link</md-icon>
                      <label>Project site URL</label>
                      <md-input md-counter="40" v-model="form.url"></md-input>
                    </md-field>

                    <md-field>
                      <label>Project logo</label>
                      <md-file placeholder="Upload project logo" v-model="form.logoName"/>
                      <md-button class="md-dense md-primary"  @click="uploadLogo()">Upload</md-button>
                    </md-field>

                    <md-checkbox v-model="form.public" class="md-primary">Public</md-checkbox>

                  </div>

                  <!-- A FAB to allow the project-view page to switch to edit mode -->
                  <!--
                  <md-button class="md-fab md-mini md-plain md-fab-bottom-right" to="/projects/edit>
                    <md-icon>edit</md-icon>
                  </md-button>
                  -->


                </md-card-content>

                <md-card-actions md-alignment="left">
                  <md-button class="md-raised md-primary" @click="submitProject()">Create Project</md-button>
                  <md-button class="md-raised md-accent">Cancel</md-button>
                </md-card-actions>



            </md-card>

          </div>


          <div class="md-layout-item md-medium-size-20 md-small-size-20 md-xsmall-size-100">

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


            -->

        <md-speed-dial class="md-bottom-right" md-direction="top">
          <md-speed-dial-target>
            <md-icon class="md-morph-initial">add</md-icon>
            <md-icon class="md-morph-final">edit</md-icon>
          </md-speed-dial-target>

          <md-speed-dial-content>
            <md-button class="md-icon-button">
              <md-icon>dvr</md-icon>
              <md-tooltip md-direction="left">Logs</md-tooltip>
            </md-button>

            <md-button class="md-icon-button">
              <md-icon>chat</md-icon>
              <md-tooltip md-direction="left">Chat</md-tooltip>
            </md-button>
          </md-speed-dial-content>
        </md-speed-dial>

        <!--
        <div class="phone-viewport">
          <md-bottom-bar md-type="shift">
            <md-bottom-bar-item id="bottom-bar-item-home" md-label="Home" md-icon="home"></md-bottom-bar-item>
            <md-bottom-bar-item id="bottom-bar-item-pages" md-label="Pages" md-icon="pages"></md-bottom-bar-item>
            <md-bottom-bar-item id="bottom-bar-item-posts" md-label="Posts"
                                md-icon="add"></md-bottom-bar-item>
            <md-bottom-bar-item id="bottom-bar-item-favorites" md-label="Favorites"
                                md-icon="favorite"></md-bottom-bar-item>
          </md-bottom-bar>
        </div>
        -->

        <div>
          <md-dialog-alert
            :md-active.sync="first"
            :md-content="dlgContent"
            md-confirm-text="OK"/>

          <md-dialog-alert
            :md-active.sync="second"
            md-title="Item Deleted"
            md-content="Your item has been <b>DELETED</b> for now..."/>

        </div>


        <md-snackbar md-position="center" :md-duration=10000 :md-active.sync="snackbarVisible" md-persistent>
          <span>{{snackbarContent}}</span>
          <md-button class="md-primary" @click="snackbarVisible = false">OK</md-button>
        </md-snackbar>

      </md-app-content>

    </md-app>
  </div>


</template>

<script>
  /* eslint-disable no-trailing-spaces */

  import axios from 'axios'

  export default {
    name: 'Sidenav',
    data: () => ({
      showNavigation: false,
      showSidepanel: false,
      first: false,
      second: false,
      snackbarVisible: false,
      snackbarContent: '',
      dlgContent: '',
      form: {name: '', desc: '', url: '', pi: '', logoName: '', logoRef: -1, public: false},
      users: []
    }),
    created () {
      this.getUsers()
    },
    methods: {
      movetoinbox () {
        this.showNavigation = false
      },
      submitProject () {
        this.dlgContent = JSON.stringify(this.form)
        this.first = true
      },
      uploadLogo () {
        const ok = Math.random()

        if (ok < 0.5) {
          this.form.logoRef = Math.round(500 * Math.random())
          this.snackbarContent = 'File: ' + this.form.logoName + ' successfully uploaded, remote fileID: ' + this.form.logoRef
          this.snackbarVisible = true
        } else {
          this.snackbarContent = 'Failed to upload logo: 504 Authorization Failure'
          this.snackbarVisible = true
        }
      },
      getUsers () {
        const url = 'https://jsonplaceholder.typicode.com/users'
        axios.get(url).then(
          reply => {
            console.log(reply.data)
            reply.data.forEach(item => { this.users.push({name: item.name, id: item.id}) })
          }).catch(
          error => {
            console.log(error)
          }
        )
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
