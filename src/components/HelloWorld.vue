<template>
	<b-container fluid class="top text-center d-flex flex-column justify-content-end">
		<b-row class="border border-info text-center d-block" style="height:10vh;display:flex;"><h1>header</h1></b-row>
		<b-row class="border border-success mt-0 pt-0" style="height:80vh;">
			<b-col sm="2" class="border border-info">
				<b-row>
					<b-col class="d-flex justify-content-between flex-column-reverse">
						<img src="../assets/logo.png" class="img img-responsive"/>
						<b-btn @click="onClick">押して</b-btn>
						<ul>
							<li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
							<li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
							<li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
							<li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
						</ul>
						<h6>Ecosystem</h6>
						<ul>
							<li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
							<li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
							<li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
							<li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
							<br>
							<li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
						</ul>
						<h6>Essential Links</h6>
						<!--h3>{{ msg }}</h3-->
					</b-col>
				</b-row>
			</b-col>
			<b-col class="px-0">
				<div class="border border-danger" style="height:80vh;overflow-y:scroll;">
					<div class="d-flex flex-column-reverse justify-content-start" id="chatlist" style="min-height:100%;">
					<div sm="12" v-for="(v, id) in arr" :key="id" class="position-static d-block">
						<h3 class="border border-info rounded py-2">
							{{id}}/{{v}}
							<input type="image" :id="'chat_' + id" src="about:blank" value="" alt="" :visible="flag" style="height:1px;width:1px;display:inline;"/>
						</h3>
					</div>
					</div>
					
					<!--b-row>
						<b-col sm="12" v-for="(v, id) in arr" :key="id" class="position-static d-block">
							<h3 class="border border-info rounded py-2">{{v}}</h3>
						</b-col>
					</b-row-->
					<!--b-row><b-col><h3 class="border border-info rounded py-5 position-sticky">hoge</h3></b-col></b-row-->
				</div>
			</b-col>
		</b-row>
		<b-row class="border border-warining text-center d-block" style="height:10vh;"><h1>footer</h1></b-row>
		<!--b-card class="h-100 w-100 p-0 m-0 d-inline-block">
			<b-card-header class="position-fixed fixed-top clearfix">header</b-card-header>
			<b-card-body class="p-0 mt-4 ml-1 mr-1 position-relative h-100 mh-100 border border-info">hoge</b-card-body>
			<b-card-footer class="fixed-bottom">footer</b-card-footer>
		</b-card-->
		<!--b-card-group class="d-flex justify-content-between flex-column" style="height:100%;">
			<b-card-header header-bg-variant="info">header</b-card-header>
			<b-card align-v="end" class="card-body d-flex justify-content-between flex-column" style="border: solid 1px green; height:100%;background-color:#eeeeee;">
				<div class="card-block" style="height:100%;background-color:#ff0000;">hoge</div>
				<b-row>foo</b-row>
				<b-row align-v="end" class="d-flex justify-content-between flex-row" style="border:solid 1px blue; height:100%; margin-bottom:0;">
					<b-col cols="4" class="d-flex justify-content-between flex-column-reverse side-nav" style="border:solid 1px red;">
						<img class="gazo" src="../assets/logo.png"/>
						<ul>
							<li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
							<li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
							<li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
							<li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
						</ul>
						<h2>Ecosystem</h2>
						<ul>
							<li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
							<li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
							<li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
							<li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
							<br>
							<li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
						</ul>
						<h2>Essential Links</h2>
						<h1>{{ msg }}</h1>
					</b-col>
				</b-row>
				<b-row style="margin-bottom:0;">bar</b-row>
			</b-card>
			<b-card-footer footer-bg-variant="success">footer</b-card-footer>
		</b-card-group-->
	</b-container>
    <!--b-alert show>Default Alert</b-alert>

    <b-alert variant="success" show>Success Alert</b-alert>

    <b-alert variant="danger"
             dismissible
             :show="showDismissibleAlert"
             @dismissed="showDismissibleAlert=false">
      Dismissible Alert!
    </b-alert>

    <b-alert :show="dismissCountDown"
             dismissible
             variant="warning"
             @dismissed="dismissCountDown=0"
             @dismiss-count-down="countDownChanged">
      <p>This alert will dismiss after {{dismissCountDown}} seconds...</p>
      <b-progress variant="warning"
                  :max="dismissSecs"
                  :value="dismissCountDown"
                  height="4px">
      </b-progress>
    </b-alert>

    <b-btn @click="showAlert" variant="info" class="m-1">
      Show alert with count-down timer
    </b-btn>
    <b-btn @click="showDismissibleAlert=true" variant="info" class="m-1">
      Show dismissible alert ({{showDismissibleAlert?'visible':'hidden'}})
    </b-btn-->
</template>

<script>
import Vue from 'vue';
import $ from 'jquery';
export default {
  name: 'HelloWorld',
  data () {
    return {
		msg: 'Hello World',
		arr: [],
		dismissSecs: 10,
		dismissCountDown: 0,
		showDismissibleAlert: false,
		flag: false
    }
  },
  methods: {
	  onClick(e){
		  this.arr.unshift(new Date());
		  const c = document.getElementById('chatlist');
		  if(c && c.scrollHeight){
			  c.scrollTop = 3000;
			  c.scroll(0, c.scrollHeight);
		      //console.log(c.scrollHeight, c.scrollTop);
			  this.flag = true;
			  Vue.nextTick(() => {
		  	  	const x = document.getElementById('chat_0');
			  	x.focus();
				  Vue.nextTick(() => {
					  x.blur();
					  this.flag = false;
				  });
			  });
		  }
		  //Vue.nextTick(() => window.setTimeout(() => window.scroll(0, $(this.$refs.chatlist).height()),300));

	  },
    countDownChanged (dismissCountDown) {
      this.dismissCountDown = dismissCountDown
    },
    showAlert () {
      this.dismissCountDown = this.dismissSecs
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.top{
	height:100vh;
	min-height:100vh;
	max-height:100vh;
}
.side-nav{
	background-color: #ddffdd;
	height:100%;
}
.gazo{
	background-color: #eeeeee;
}
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
