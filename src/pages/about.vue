<template>
	<v-container fluid>
		<v-card raised>
			<v-layout row wrap>
				<v-flex xs12 sm4 md3 lg2>
					<v-card-media src="/public/img/avatar2.jpg" height="100%" class="hidden-xs-only"></v-card-media>
					<v-card-media src="/public/img/avatar2.jpg" height="200px" class="hidden-sm-and-up"></v-card-media>
				</v-flex>
				<v-flex xs12 sm8 md9 lg10>
					<v-card-title>
						<div class="headline">{{name}}</div>
					</v-card-title>
					<v-container>
						<p v-html="desc"></p>
						<v-divider></v-divider>
						<v-list ripple>
							
						</v-list>
					</v-container>
				</v-flex>
			</v-layout>
		</v-card>
	</v-container>
</template>

<script>
	export default {
		data: () => ({
			name: 'Eduardo Alves da Silva',
			desc: `
				Tenho ${idade(28, 4, 1994)} anos de idade.<br>
				Curso Bacharelado em Computação no Instituto Federal de Brasília.<br>
			`,
			social: {
				facebook: 'https://www.facebook.com/EduardoAlveSilva',
				github: 'https://github.com/alvesil',
				email: 'alvesil.eduardo.silva@gmail.com',
				phone: '(61) 9 9860-0715',
				linkedin: 'https://www.linkedin.com/in/eduardo-alves-21084515b/'
			}
		})
	}

	function idade(d, m, y){
		let D = new Date()
		let cY = D.getFullYear()
		let cM = D.getMonth() + 1
		let cD = D.getDate()
		let age = cY - y
		if(cM < m || cM == m && cD < d){
			age--
		}
		return age
	}
</script>
