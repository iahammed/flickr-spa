<template>
	<div class="container-fluid">
		<div class="jumbotron jumbotron-fluid">
		    <div class="container">
		      <form class="form-inline" >
		      	<div class="input-group col-lg-12 col-sm-12 col-sm-12 col-xs-12">
  					<input type="text" 
  						class="form-control col-lg-12 col-sm-12 col-sm-12 col-xs-12" v-model='tag'
  						placeholder="Search for pictures in Flickr’s public API using tags" aria-label="Recipient's username" aria-describedby="basic-addon2"
  						@blur="blurKeywords">
  					<!-- <div class="input-group-append">
    					<button class="btn btn-outline-secondary">Button</button>
  					</div> -->
				</div>
		        
		      </form>
		    </div>
		  </div>
		<div class="row">
			<div v-if="photos == ''" class="container">
				<h2>Loading...</h2>
				<p>If takes too long probably you might need to download <br/>
					<strong> Allow-Control-Allow-Origin </strong><br />
					from<br />
					<strong>Chrome web-store </strong><br />
					* because its a local development
				</p>
				<a class = "btn btn-success" href="https://chrome.google.com/webstore/detail/allow-control-allow-origi/nlfbmbojpeacfghkpbjhddihlkkiljbi?hl=en">Get Chrome web-store : Allow-Control-Allow-Origin</a>
				
			</div>
			<div class="col-xl-4 col-lg-4 col-md-6 col-sm-12 col-xs-12" v-for="photo in photos">
				<div class="card-deck">
					<div class="card">
					  	<img :src="photo.media.m" class="responsive">
					  	<div class="card-body">
					    	<h4 class="card-title">{{ photo.title }}</h4>
					  	</div>
					</div>
				</div>

			</div>	
		</div>
	</div>
</template>

<script>
	
import axios from 'axios'

export default {
	name: 'Result',
	data() {
	    return {
	    	tag:'',
	      	photos:[],
	      	myData:'',
	      	token:'',
	      	url: 'http://api.flickr.com/services/feeds/photos_public.gne?tags=cats&format=json&nojsoncallback=true'
	    }
	},
	mounted() {
		axios.get(this.url).then( response => { this.photos = response.data.items })
	},
  	methods: { 
  		blurKeywords(){
  		let url = 'http://api.flickr.com/services/feeds/photos_public.gne?tags=' 
  					+ this.tag + 
  					'&format=json&nojsoncallback=true'
				axios.get(url).then( response => { this.photos = response.data.items })
  		}
  	}
}
</script>
<style>
	.img {
	    width: 100%;
	    height: auto;
	    /*max-height: 10px;*/
	}
	.card-title{
		max-height: 25px;
		overflow: hidden;
	}

</style>

