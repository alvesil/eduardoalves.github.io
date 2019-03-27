<template>
	<v-container fluid grid-list-lg>
		<v-layout row wrap>
			<v-flex xs12>
				<v-btn outline color="primary" :href="cv" target="_blank"><v-icon>mdi-download</v-icon> PDF</v-btn>
				<v-btn outline color="primary" :href="lattes" target="_blank">Lattes</v-btn>
			</v-flex>
			<v-flex xs12 sm6 md4 lg3 d-flex v-for="(section, i) in sections" :key="i">
				<v-card raised>
					<v-card-title>
						<div class="headline">{{section.title}}</div>
					</v-card-title>
					<v-container>
						<div v-for="(item, i) in section.items" :key="i">
							<b>{{item.name}}</b><br>
							{{item.desc}}
							<div v-if="i != section.items.length - 1">
								<v-divider></v-divider><br>
							</div>
						</div>
					</v-container>
				</v-card>
			</v-flex>
		</v-layout>
	</v-container>
</template>

<script>
export default {
	data: () => ({
		cv: '/public/doc/cv.pdf',
		lattes: 'http://lattes.cnpq.br/2530145213203050',
		sections: [
			{
				title: 'Tecnologias',
				items: [
					{
						name: 'Linguagens/Plataformas/Frameworks',
						desc: 'HTML, CSS, C, Java Android'
					},
					{
						name: 'Sistemas Operacionais',
						desc: 'Windows, Linux'
					},
					{
						name: 'Informática Básica',
						desc: 'Pacote Office, Internet e Montagem e Configuração de Micro e Configuração de Redes'
					},

				]
			},
			{
				title: 'Experiências Profissionais',
				items: [
					{
						name: 'Estágio Nível Médio',
						desc: 'Superior Tribunal de Justiça (STJ) | 2011 - 2012'
					},
					{
						name: 'Supervisor de Agência',
						desc: 'A&M Cargas e Turismo | 2013 - 2014'
					},
					{
						name: 'Técnico em Telecomunicações',
						desc: 'AABP/TIGER Segurança Eletrônica | 2015 - 2016'
					}
				]
			},
			{
				title: 'Formação',
				items: [
					{
						name: 'Ensino Fundamental',
						desc: 'CEF 25 - Ceilândia - DF | 2001 - 2009'
					},
					{
						name: 'Ensino Médio',
						desc: 'CEM 12 - Ceilândia - DF | 2010 - 2012'
					},
					{
						name: 'Ensino Técnico',
						desc: 'ETB Escola Técnica de Brasília | 2014 - 2016'
					},
					{
						name: 'Bacharelado em Ciência da Computação',
						desc: 'IFB Campus Taguatinga | 2015 - Agora'
					}
				]
			},
			{
				title: 'Formação Complementar',
				items: [
					{
						name: 'Programação Android',
						desc: '#BORAVENCER | 2017 - 2017'
					}
				]
			},
			{
				title: 'Idiomas',
				items: [
					{
						name: 'Inglês',
						desc: 'Intermediário'
					},
					{
						name: 'Espanhol',
						desc: 'Básico'
					}
				]
			}
		]
	})
}
</script>
