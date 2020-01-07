<template>
    <q-layout>
      <q-header elevated class="bg-white text-grey-7">
         <div class ="row">
           <q-toolbar>
           <div class="col q-pl-md">
             <img alt="logo" src="https://cdn.zeplin.io/5e131414d527b90e8289ff59/assets/36FB8F84-59EA-4D6F-870C-166826FD5B85.svg" />
           </div>
           <div class="col">
               <q-btn stretch flat  icon="img:statics/icons/alarm.svg"/>Recent
           </div>
           <div class="is-divider-vertical" data-content="OR"></div>
           <div class="col">
         <q-btn stretch flat icon="img:statics/icons/star.svg"/>Trending
           </div>
           <div class="col">
         <q-btn stretch flat  icon="img:statics/icons/signal.svg"/>Pulse Poll
           </div>
                     <div class="col q-pa-md">
         <q-btn unelevated rounded color="primary" class="q-mr-md" label="Add Post" />
         <q-btn flat round  class="q-mr-md" icon="img:statics/icons/search.svg" />
         <q-btn flat round  class="q-mr-md" icon="img:statics/icons/notification.svg" />
         <q-btn flat round  class="q-mr-md" icon="img:statics/icons/user-dropdown.svg" style="width: auto" />
        </div>
         </q-toolbar>
        </div>
         </q-header>
      <q-drawer
        v-model="drawer"
        show-if-above
        :mini="miniState"
        @mouseover="miniState = false"
        @mouseout="miniState = true"
        mini-to-overlay
        :height="80"
        :width="200"
        :breakpoint="500"
        bordered
        content-class="bg-white"
        class="text-grey-7"
      >
        <q-scroll-area class="fit">
          <q-list>
             <q-item clickable >
              <q-item-section avatar>
               <q-icon  name="img:statics/assets/discussion.svg" />
              </q-item-section>
              <q-item-section >
                Discussion
                <q-list>
                  <q-item clickable v-close-popup @click="onItemClick">
                     <q-icon class="q-mr-md"  name="img:statics/icons/sort.svg" />
                     <q-item-label >General</q-item-label>
                  </q-item>
                  <q-item clickable v-close-popup @click="onItemClick">
                     <q-icon  class="q-mr-md"  name="img:statics/icons/sort.svg" /> <q-item-label>Announcement</q-item-label>
                    </q-item>
                  <q-item clickable v-close-popup @click="onItemClick">
                     <q-icon  class="q-mr-md" name="img:statics/icons/sort.svg" /> <q-item-label>Random</q-item-label>
                  </q-item>
                   <q-item clickable v-close-popup @click="onItemClick">
                     <q-icon class="q-mr-md"  name="img:statics/icons/plus.svg" /> <q-item-label>Add Channel</q-item-label>
                    </q-item>
                </q-list>
              </q-item-section>
    </q-item>
            <q-separator />
            <q-item clickable >
              <q-item-section avatar>
          <img src="../assets/approval.svg" />
              </q-item-section>
              <q-item-section>
                For Approval
            </q-item-section>
            </q-item>
            <q-separator />
            <q-item clickable >
              <q-item-section avatar>
          <img src="../assets/reported.svg" />
              </q-item-section>

              <q-item-section>
                Reported Posts
              </q-item-section>
            </q-item>
             <q-separator />
            <q-item clickable>
              <q-item-section avatar>
          <img src="../assets/members.svg" />
              </q-item-section>

              <q-item-section>
                Members
              </q-item-section>
            </q-item>
             <q-separator />
            <q-item clickable>
              <q-item-section avatar>
          <img src="../assets/members.svg"/>
              </q-item-section>
              <q-item-section>
                Apps
              </q-item-section>
            </q-item>
          </q-list>
        </q-scroll-area>
      </q-drawer>

      <q-page-container>
        <q-page padding>
          <div id="app">
  <Panel>
      <General></General>
  </Panel></div>
        </q-page>
      </q-page-container>
    </q-layout>
</template>
<script>
import General from '../components/general.vue'
export default {
  components: {
    General
  },
  data () {
    return {
      drawer: false,
      miniState: true
    }
  }
}
</script>
