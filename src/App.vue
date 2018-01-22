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
              <md-list-item class="md-inset">MASSMO</md-list-item>
              <md-list-item class="md-inset">OSNAP</md-list-item>
              <md-list-item class="md-inset">ALTER-ECO</md-list-item>
              <md-list-item class="md-inset">EEL</md-list-item>
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
            <span>Project {{edit ? 'editing' : 'creation'}} form</span>
            <md-card md-with-hover>

              <md-card-header class="md-accent">
                <div class="md-title">


                  <md-button class="md-icon-button md-primary">
                    <md-icon>{{edit ? 'edit' : 'library_add'}}</md-icon>
                  </md-button>

                  {{ edit ? 'Edit existing Project' : 'Add a new Project'}}


                </div>
                <div class="md-subhead">Projects contain campaigns</div>
              </md-card-header>

              <md-card-content>

                <!-- Form elements here -->
                <div>

                  <!-- NAME -->
                  <md-field md-clearable>
                    <label>Name</label>
                    <md-input md-counter="30" v-model="form.name"></md-input>
                  </md-field>

                  <!-- SHORT NAME -->
                  <md-field md-clearable>
                    <label>Short Name</label>
                    <md-input md-counter="30" v-model="form.shortName"></md-input>
                  </md-field>

                  <!-- P INVSTIG -->
                  <md-field>
                    <label>Principle Investigator</label>
                    <md-select name="piuser" v-model="form.pi">
                      <md-option v-for="(u, index) in users" :value="u.id" :key="index">{{u.name}}</md-option>
                    </md-select>
                  </md-field>

                  <!-- PRIM ORG-->
                  <md-field class="widesel">
                    <label>Primary Organization (C75)</label>
                    <md-select name="projorg" v-model="form.primOrg">
                      <md-option v-for="(o, index) in orgs" :value="o.id" :key="index">{{o.name}}</md-option>
                    </md-select>
                  </md-field>

                  <!-- PRIM ORG CTRY-->
                  <md-field class="widesel">
                    <label>Primary Organization Country (C32)</label>
                    <md-select name="projctry" v-model="form.primCntry">
                      <md-option v-for="(c, index) in countries" :value="c.id" :key="index">{{c.name}}</md-option>
                    </md-select>
                  </md-field>

                  <!-- GEOG AREA-->
                  <md-field class="widesel">
                    <label>Geographic Area (C19)</label>
                    <md-select name="projgeog" v-model="form.geogArea">
                      <md-option v-for="(g, index) in geog" :value="g.id" :key="index">{{g.name}}</md-option>
                    </md-select>
                  </md-field>

                  <!-- OCEAN DISCIPLINE-->
                  <md-field class="widesel">
                    <label>Oceanographic Discipline (P08)</label>
                    <md-select name="projdisc" v-model="form.disc">
                      <md-option v-for="(d, index) in disciplines" :value="d.id" :key="index">{{d.name}}</md-option>
                    </md-select>
                  </md-field>

                  <!-- FUNDER-->
                  <md-field class="widesel">
                    <label>Funding Organization (C75)</label>
                    <md-select name="projfund" v-model="form.fundOrg">
                      <md-option v-for="(o, index) in orgs" :value="o.id" :key="index">{{o.name}}</md-option>
                    </md-select>
                  </md-field>

                  <!-- START DATE -->
                  <md-field>
                    <label>Start date</label>
                    <md-datepicker v-model="form.startDate"/>
                  </md-field>

                  <!-- END DATE -->
                  <md-field>
                    <label>End date</label>
                    <md-datepicker v-model="form.endDate"/>
                  </md-field>

                  <!-- DESCRIPTION -->
                  <md-field>
                    <label>Description</label>
                    <md-textarea required v-model="form.desc"></md-textarea>
                    <i class="md-helper-text">Enter lots of information</i>
                  </md-field>

                  <!-- SITE URL -->
                  <md-field md-clearable>
                    <md-icon class="md-primary">link</md-icon>
                    <label>Project site URL</label>
                    <md-input md-counter="40" v-model="form.url"></md-input>
                  </md-field>

                  <!-- LOGO -->
                  <md-field>
                    <label>Project logo</label>
                    <md-file placeholder="Upload project logo" v-model="form.logoName"/>
                    <md-button class="md-dense md-primary" @click="uploadLogo()">Upload</md-button>
                  </md-field>

                  <!-- PUBLIC -->
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
                <md-button class="md-raised md-primary" @click="submitProject()">{{edit ? 'Update' : 'Create'}}
                  Project
                </md-button>
                <md-button class="md-raised md-accent">Cancel</md-button>
              </md-card-actions>


            </md-card>

          </div>


          <div class="md-layout-item md-medium-size-20 md-small-size-20 md-xsmall-size-100">

          </div>


        </div>

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

            <md-button class="md-icon-button" @click="toggleEdit()">
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
  import moment from 'moment'

  export default {
    name: 'Sidenav',
    data: () => ({
      edit: false,
      showNavigation: false,
      showSidepanel: false,
      first: false,
      second: false,
      snackbarVisible: false,
      snackbarContent: '',
      dlgContent: '',
      form: {
        name: '',
        shortName: '',
        desc: '',
        url: '',
        pi: '',
        primOrg: '',
        primCntry: '',
        geogArea: '',
        disc: '',
        fundOrg: '',
        startDate: new Date(),
        endDate: null,
        logoName: '',
        logoRef: -1,
        public: false
      },
      users: [],
      orgs: [],
      countries: [],
      disciplines: [],
      geog: []
    }),
    created () {
      this.getUsers()
      this.getOrgs()
      this.getCountries()
      this.getDisciplines()
      this.getGeog()
    },
    methods: {
      movetoinbox () {
        this.showNavigation = false
      },
      submitProject () {
        let sd = moment(this.form.startDate)
        const sdtxt = sd.format('YYYY-MM-DDTHH:mm:ss')
        this.form.startDate = sdtxt
        let ed = moment(this.form.endDate)
        const edtxt = ed.format('YYYY-MM-DDTHH:mm:ss')
        this.form.endDate = edtxt
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
        // const url = 'https://jsonplaceholder.typicode.com/users'
        const url = 'http://openboatmonitor.org/obportal/api/get_users.php'
        axios.get(url).then(
          reply => {
            console.log(reply)
            reply.data.data.forEach(item => {
              this.users.push({name: item.name, id: item.id})
            })
          }).catch(
          error => {
            console.log(error)
          }
        )
      },
      getOrgs () {
        console.log('Get orgs from nerc vocab sever...')
        const url = 'http://vocab.nerc.ac.uk/collection/C75/current/'
        const proxyurl = 'https://cors-anywhere.herokuapp.com/'

        axios.get(proxyurl + url).then(
          reply => {
            let parser = new DOMParser()
            let doc = parser.parseFromString(reply.data, 'text/xml')  // or could be application/xml

            const root = doc.documentElement.getElementsByTagName('skos:member')

            // loop over the member nodes
            for (let i = 0; i < root.length; i++) {
              const cc = root[i]
              const membersub = cc.childNodes

              // loop over subnodes of member i
              for (let k = 0; k < membersub.length; k++) {
                const cmk = membersub[k]

                if (cmk.nodeName === 'skos:Concept') {
                  const cmkj = cmk.childNodes

                  let notat = ''
                  let orgname = ''
                  for (let j = 0; j < cmkj.length; j++) {
                    let cj = cmkj[j]
                    // found a notation log it
                    if (cj.nodeName === 'skos:notation') {
                      notat = cj.childNodes[0].nodeValue
                    }

                    // found a preflabel keep it
                    if (cj.nodeName === 'skos:prefLabel') {
                      const cjtext = cj.childNodes[0].nodeValue
                      orgname = cjtext
                    }

                    if (cj.nodeName === 'skos:broader') {
                      const cattr = cj.attributes
                      const cat0 = cattr[0]

                      if (cat0.value === 'http://vocab.nerc.ac.uk/collection/C32/current/GB/') {
                        this.orgs.push({id: notat, name: notat + ' - ' + orgname})
                      }
                    }
                  }
                }
              }
            }
          }).catch(
          error => {
            console.log(error)
          }
        )
      },
      getCountries () {
        console.log('Get countries from nerc vocab sever...')
        const url = 'http://vocab.nerc.ac.uk/collection/C32/current/'
        const proxyurl = 'https://cors-anywhere.herokuapp.com/'

        axios.get(proxyurl + url).then(
          reply => {
            let parser = new DOMParser()
            let doc = parser.parseFromString(reply.data, 'text/xml')  // or could be application/xml

            const root = doc.documentElement.getElementsByTagName('skos:member')

            // loop over the member nodes
            for (let i = 0; i < root.length; i++) {
              const cc = root[i]
              const membersub = cc.childNodes

              // loop over subnodes of member i
              for (let k = 0; k < membersub.length; k++) {
                const cmk = membersub[k]

                if (cmk.nodeName === 'skos:Concept') {
                  const cmkj = cmk.childNodes

                  let notat = ''
                  let orgname = ''
                  for (let j = 0; j < cmkj.length; j++) {
                    let cj = cmkj[j]
                    // found a notation log it
                    if (cj.nodeName === 'skos:notation') {
                      notat = cj.childNodes[0].nodeValue
                    }

                    // found a preflabel keep it
                    if (cj.nodeName === 'skos:prefLabel') {
                      const cjtext = cj.childNodes[0].nodeValue
                      orgname = cjtext
                      this.countries.push({id: notat, name: notat + ' - ' + orgname})
                      console.log('Add country: ' + orgname)
                    }
                  }
                }
              }
            }
          }).catch(
          error => {
            console.log(error)
          }
        )
      },
      getDisciplines () {
        console.log('Get disciplines from nerc vocab sever...')
        const url = 'http://vocab.nerc.ac.uk/collection/P08/current/'
        const proxyurl = 'https://cors-anywhere.herokuapp.com/'

        axios.get(proxyurl + url).then(
          reply => {
            let parser = new DOMParser()
            let doc = parser.parseFromString(reply.data, 'text/xml')  // or could be application/xml

            const root = doc.documentElement.getElementsByTagName('skos:member')

            // loop over the member nodes
            for (let i = 0; i < root.length; i++) {
              const cc = root[i]
              const membersub = cc.childNodes

              // loop over subnodes of member i
              for (let k = 0; k < membersub.length; k++) {
                const cmk = membersub[k]

                if (cmk.nodeName === 'skos:Concept') {
                  const cmkj = cmk.childNodes

                  let notat = ''
                  let orgname = ''
                  for (let j = 0; j < cmkj.length; j++) {
                    let cj = cmkj[j]
                    // found a notation log it
                    if (cj.nodeName === 'skos:notation') {
                      notat = cj.childNodes[0].nodeValue
                    }

                    // found a preflabel keep it
                    if (cj.nodeName === 'skos:prefLabel') {
                      const cjtext = cj.childNodes[0].nodeValue
                      orgname = cjtext
                      this.disciplines.push({id: notat, name: notat + ' - ' + orgname})
                      console.log('Add disc: ' + orgname)
                    }
                  }
                }
              }
            }
          }).catch(
          error => {
            console.log(error)
          }
        )
      },
      getGeog () {
        console.log('Get geo-areas from nerc vocab sever...')
        const url = 'http://vocab.nerc.ac.uk/collection/C19/current/'
        const proxyurl = 'https://cors-anywhere.herokuapp.com/'

        axios.get(proxyurl + url).then(
          reply => {
            let parser = new DOMParser()
            let doc = parser.parseFromString(reply.data, 'text/xml')  // or could be application/xml

            const root = doc.documentElement.getElementsByTagName('skos:member')

            // loop over the member nodes
            for (let i = 0; i < root.length; i++) {
              const cc = root[i]
              const membersub = cc.childNodes

              // loop over subnodes of member i
              for (let k = 0; k < membersub.length; k++) {
                const cmk = membersub[k]

                if (cmk.nodeName === 'skos:Concept') {
                  const cmkj = cmk.childNodes

                  let notat = ''
                  let orgname = ''
                  for (let j = 0; j < cmkj.length; j++) {
                    let cj = cmkj[j]
                    // found a notation log it
                    if (cj.nodeName === 'skos:notation') {
                      notat = cj.childNodes[0].nodeValue
                    }

                    // found a preflabel keep it
                    if (cj.nodeName === 'skos:prefLabel') {
                      const cjtext = cj.childNodes[0].nodeValue
                      orgname = cjtext
                      this.geog.push({id: notat, name: notat + ' - ' + orgname})
                      console.log('Add geog: ' + orgname)
                    }
                  }
                }
              }
            }
          }).catch(
          error => {
            console.log(error)
          }
        )
      },
      toggleEdit () {
        this.edit = !this.edit
        if (this.edit) {
          this.form.name = 'MASSMO'
          this.form.pi = 4
          this.form.desc = 'A very interseting ptroject'
        }
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

  .widesel {
    width: 45em;
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
