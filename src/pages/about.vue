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
							<v-list-tile :href="social.facebook" target="_blank">
								<v-list-tile-avatar>
									<v-icon>mdi-facebook</v-icon>
								</v-list-tile-avatar>
								<v-list-tile-title>Facebook</v-list-tile-title>
							</v-list-tile>
							<v-list-tile :href="social.instagram" target="_blank">
								<v-list-tile-avatar>
									<v-icon>mdi-instagram</v-icon>
								</v-list-tile-avatar>
								<v-list-tile-title>Instagram</v-list-tile-title>
							</v-list-tile>
							<v-list-tile :href="social.linkedin" target="_blank">
								<v-list-tile-avatar>
									<v-icon>mdi-linkedin</v-icon>
								</v-list-tile-avatar>
								<v-list-tile-title>Linkedin</v-list-tile-title>
							</v-list-tile>
							<v-list-tile :href="social.github" target="_blank">
								<v-list-tile-avatar>
									<v-icon>mdi-github-circle</v-icon>
								</v-list-tile-avatar>
								<v-list-tile-title>GitHub</v-list-tile-title>
							</v-list-tile>
							<v-list-tile :href="`mailto://${social.email}`">
								<v-list-tile-avatar>
									<v-icon>mdi-email</v-icon>
								</v-list-tile-avatar>
								<v-list-tile-title>{{social.email}}</v-list-tile-title>
							</v-list-tile>
							<v-list-tile :href="`tel://${social.phone}`">
								<v-list-tile-avatar>
									<v-icon>mdi-whatsapp</v-icon>
								</v-list-tile-avatar>
								<v-list-tile-title>{{social.phone}}</v-list-tile-title>
							</v-list-tile>
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
				Possuo conhecimentos intermediários em HTML, CSS, JavaScript, PHP, MySQL e Bootstrap.
			`,
			social: {
				facebook: 'https://www.facebook.com/EduardoAlveSilva',
				instagram: 'https://www.instagram.com/alvesil.eduardo/',
				github: 'https://github.com/alvesil',
				email: 'alvesil.eduardo.silva@gmail.com',
				phone: '(61) 9 9928-9003',
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
