<template>
    <q-layout>
      <q-header elevated class="bg-white text-grey-7">
         <div class ="row">
           <q-toolbar>
           <div class="col">
                       <img alt="logo" src="../assets/logo.svg" style="padding-left:2%; padding-right:2%"/>
           </div>
           <div class="col">
               <q-btn stretch flat  icon="img:statics/icons/Union 17.svg"/>Recent
           </div>
           <div class="is-divider-vertical" data-content="OR"></div>
           <div class="col">
         <q-btn stretch flat icon="img:statics/icons/Path 10142.svg"/>Trending
           </div>
           <div class="col">
         <q-btn stretch flat  icon="img:statics/icons/Asset13.svg"/>Pulse Poll
           </div>
           <div class="col">
         <q-btn unelevated rounded color="primary" label="Add Post" />
         <q-btn flat round  icon="img:statics/icons/Asset9.svg" />
         <q-btn flat round  icon="img:statics/icons/Asset8.svg" />
         <q-btn flat round icon="img:statics/icons/Asset23.svg" style="width: auto !important" />
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
          <q-list padding>
            <q-item active clickable>
              <q-item-section avatar>
          <img src="../assets/discussion.svg" />
              </q-item-section>
              <q-item-section>
                Discussion
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
          <img src="../assets/Group 8150.svg"/>
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
          <p v-for="n in 15" :key="n">
          </p>
        </q-page>
      </q-page-container>
    </q-layout>
</template>
<script>
export default {
  data () {
    return {
      drawer: false,
      miniState: true
    }
  }
}
</script>
