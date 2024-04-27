# Ponderada de Programação: MVC #

### Título do Projeto: "Projeto Abandono Zero" ###

Descrição: O INSPA está lançando o "Projeto Abandono Zero" com o propósito de compreender as razões por trás do abandono de animais. Para alcançar esse objetivo, estamos desenvolvendo um website integrado a um banco de dados para coletar informações de usuários, incluindo aqueles que atualmente possuem, já tiveram, pretendem ter, ou nunca tiveram cachorros. Com base nessas informações, será gerado um relatório para que os pesquisadores possam analisar e identificar as causas subjacentes ao abandono.

Arquitetura: O projeto seguirá o modelo MVC (Model-View-Controller) para garantir uma organização eficiente e uma separação clara das camadas de dados, apresentação e lógica de negócios.

Ferramenta de Diagramação: Utilizaremos o Draw.io para criar e visualizar os diagramas arquiteturais e de fluxo de dados necessários para o desenvolvimento e implementação do projeto.


## Modelos (Models): ##

O componente Model é encarregado da gestão e manipulação dos dados. Assim, ele controla as informações fornecidas pelo usuário, armazenando dados como:

- Id do Usuário
- Nome do Usuário
- Senha
- Email
- Dados
- Criar Usuário
- Criar Senha
- Verificar Senha
- Verificar Usuário
- Verificar se é Admin

## Controladores (Controllers): ##

Os controladores (controllers) são encarregados de administrar as interações entre o Model e a View. Eles interpretam as solicitações do usuário e coordenam as operações necessárias nos Models, antes de enviar os dados processados para a View. O projeto foi segmentado em três controladores, que são:

- Usuários: Executam operações após as ações dos usuários, como registrar as informações fornecidas (cadastro ou login) e simultaneamente validá-las. Assim, as informações de cadastro e login são recebidas pelo controlador, validadas e enviadas ao banco de dados.

- Pesquisadores: Realizam operações após as ações dos pesquisadores, como concluir o processo ou aplicar filtros. Nesse sentido, o controlador identifica quando os botões de filtro ou conclusão são ativados e executa as respectivas ações.

- Informações: Efetuam operações após as ações dos usuários dentro do formulário. Dessa maneira, as respostas são registradas e a progressão do questionário é validada. Em seguida, o controlador recebe as respostas do formulário e as encaminha para o Model, que as registra no banco de dados.

## Vizualização (Views) ##

A camada de visualização (View) inclui todas as páginas que serão exibidas ao usuário. Inicialmente, desenvolvemos vários elementos essenciais para a construção do site, os quais variam conforme a página em que o usuário se encontra. No geral, esses elementos são:

- Botão de Sobre (Permite que o usuário vá para a aba informativa do site)
- Carrosel (Método de vizualizar informações em sites)
- Botão de Login (Permite que o usuário vá para a aba de login do site)
- Texto sobre (Texto informativo do site)
- Imagens
- Navbar (Barra que permite a navegação facilitada no site)
- Perguntas (Perguntas do site)
- Respostas (Permite que usuário insira suas respostas das perguntas)
- Botão enviar (Permite que o usuário envie suas respostas ao banco de dados)
- Gráfico (Vizualização dos dados coletados)
- Estatísticas (Vizualização das estatísticas coletadas)
- Botão baixar (Permite que o usuário baixe os gráficos e estatísticas em seu dispositivo)

Todas essas vizualizações estão disponíveis no site, porém diferentes tipos de usuários teram diferentes tipos de acessos a essas vizualizações. Nesse sentido, podemos tomar como exemplo um usuário normal, que apenas preenche o formulário, e um pesquisador com acesso de administrador. Esses dois tipos de usuário teram acesso a abas diferentes, por exemplo o usuário padrão não terá acesso a aba de gráficos e estatísticas.

## Consequências da Arquitetura ##

A adoção do Sails.js facilita o desenvolvimento detalhado e rápido de aplicativos web e APIs. Isso resulta em uma separação mais clara das camadas de software, proporcionando um entendimento mais profundo da aplicação.

As tecnologias empregadas também favorecem uma maior escalabilidade, pois a divisão em camadas permite uma melhor manutenção do código, que pode ser organizado e testado de forma independente.

## Infraestrutura: ##

Para iniciar, o projeto utiliza o sistema de gerenciamento de banco de dados relacional denominado PostgreSQL. Este banco de dados é responsável por armazenar as tabelas contendo as respostas. Além disso, o MVC está incorporado no Modelo (Model), garantindo que este nunca será acessado pelo usuário. Apenas os pesquisadores terão acesso a esses dados ao final do processo.