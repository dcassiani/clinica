
\php-builtin
- é um servidor PHP leve, pra testes locais rápidos... não devemos subir jamais no site... mas fique a vontade se quiser montar um outro Apache PHP pra vc
- inicie o servidor com o comando no prompt do windows: run.bat ---- ele vai te iniciar no URL: http://localhost/isoldi-correa-com/index.php
- no \php-builtin\run.bat, antes de executar a 1a vez, edite o bat e acerte o caminho do próprio run.bat

fotos da equipe: 
\php-builtin\isoldi-correa-com\images\profissionais

- precisamos pegar aquelas fotos do Google Drive que o fotografo enviou e cortar nos mesmo tamanhos - bom fazer que nem o leticiaberlim.jpg, 3 cortes pra cada profissional pra no futuro já aproveitar pra Rede Social: 1x focando no meio do peito pra cima, focando no rosto, focando na pose
- depois essas fotos vão inicialmente pro carrossel que está na Home: persons-carrousel.php (por hora estático, vai ter pouca ou nenhuma atualização isso, mas vamos melhorar no futuro com mais dados do currículo de cada profissional) (no futuro proximo, vamos ter uma parte de conteudo com o curriculos da equipe tb)


\php-builtin\isoldi-correa-com\includes
- coração do PHP do site
- vc abrindo o php-builtin\isoldi-correa-com\index.php vai ver todos os includes... dá uma estudada no que cada um faz, mas basicamente são pedaços da home, mas separados para poderem serem reaproveitados como necessário

estou montando uma pagina que recebe um parametro do nome do arquivo de conteudo para ser lido
exemplo: http://localhost/isoldi-correa-com/artigo.php?ct=teste
tudo nesse PHP é reaproveitado da home, exceto isso:
	include 'includes/content-text-only.php';
que é o include que efetivamente tem o teste de comandos iniciais pra encontra no diretorio-chave e ler um json com o mesmo nome. Dá uma estudada nele.

depois que entender, o objetivo é entrar nesse diretório com varios conteudos em forma de texto:
\php-builtin\isoldi-correa-com\jsondb
- precisamos formatar cada parágrafo para ser um item de json, formando uma ARRAY de paragrafos. Bom por um campo específico com o titulo também, só pra diferenciar
- depois, adaptar esse content-text-only.php pra então fazer um LOOP nessa array, e exibir o titulo... como adaptar digo fazer um layout bonitinho para que o PHP repita pra quantos parágrafos forem necessários no Bootstrap/HTML
- a ideia do artigo.php é ter a estrutura reduzida do que é a Home, mas mantendo o mesmo layout e Responsividade (aperte F12 no seu Chrome e alterne pra diversos layout de celular, além do site completo, sempre teste pra ficar bonitinho em diversos tamanhos, seja pra computador ou celular). Além disso, mais pra frente, teremos outros templates mais trabalhados, e jsons (ou migraremos pra um MySQL) com mais campos, como imagens, links, e outras formatações de conteudo... mas vamos começar do texto e titulo.
- quando isso ficar pronto, vamos cadastrar no menu \php-builtin\isoldi-correa-com\includes\navbar.php os links pra /artigo.php?ct=XXXXXXX pra cada json de conteudo

\php-builtin\isoldi-correa-com\includes\footer.php
- além de ser o rodapé geral do site, tem a importação do Bootstrap: core-js.php e tem o structuredDataJson.php
- structuredDataJson.php  = importantissimo pro Google indexar com boa pontuação... se baseia naquela estrutura do Schema.org que te passei antes. Vamos aprimorar isso no futuro próximo pra acertar o SEO.


\php-builtin\isoldi-correa-com
sitemap.xml e robots.txt - são do SEO do Google... precisamos rever/estudar como escreve isso de maneira que o Google pontue bem a gente... prioridade baixa enquanto a artigo.php não estiver funcionando distribuindo conteudo