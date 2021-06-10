<h3><center>CONTROLE E ECONOMIA: ATENUAÇÃO E CONTROLE DE ENERGIA GASTO COM ILUMINAÇÃO EM RESIDÊNCIAS E COMÉRCIOS</center></h3>

<b>Aluno :</b>  Daniel Pedrosa Santos 			<b>R.A.:</b> 1460281723011

<h1>Problema</h1>
<p align=”Justify”>
	Consumo desnecessário de energia em iluminação nas residências e/ou pequenos comércios.
</p>
<div>
<h1>Motivação</h1>
<p align=”Justify”>
	Considerando que o gasto mínimo com iluminação elétrica em residências no Brasil seja em torno 3% a 3,6% do gasto total e que o custo de 1 KW/h a cada dia que passa vem ficando mais caro, qualquer economia para a família e/ou pequeno empresário pode ser interessante. Tendo uma visão um pouco maior, a economia sobre o total de consumo de 3 a 3,5% no país todo, já representaria um montante econômico representativo. Esta economia com o custo em energia elétrica vem sendo cada vez mais importante a todos e não apenas no Brasil. Devemos sim considerar já que não seria uma economia simplista pois, segundo a Empresa de Pesquisa Energética (EPE), foram consumidos no Brasil em 2019 em energia elétrica, em torno de 482.083 GWh, deste montante considerando apensa residência e comércio o montante de 234.102 GWh o que representaria uma economia de cerca de 7.023 GWh representando assim um potencial econômico e ambiental relevantes a todos sejam diretamente ou indiretamente.
	Exemplificando de uma maneira mais prática este gasto no dia a dia de uma residência, casa onde o morador (seja ele adulto, adolescentes e/ou crianças), possui acesso ao interruptor para ligar/desligar a iluminação sem nenhuma restrição, quando não apagadas após a utilização podem ficar por horas ligadas sem nenhuma utilização consumindo energia desnecessariamente. Agora veja você neste mesmo cenário citado anteriormente, porém com um agravante, no cômodo onde foi acionado o(s) interruptor(es) possui luz do tipo spot, onde normalmente possuem mais de uma lâmpada no cômodo (podendo chegar a 5 ou mais no mesmo cômodo), e todas estas lâmpadas ligadas desnecessariamente.
	Em uma análise feita pelo Laboratório de Eficiência Energética em Edificações (LabEEE), localizado na Universidade Federal de Santa Catarina com base nos dados obtidos em uma pesquisa por amostragem da PROCEL/Eletrobras foi estimada que o percentual do consumo energético de uma residência no Brasil estaria em torno 5,5%, tornando o nosso valor estimado para trabalhar a economia no gasto com energia elétrica ainda maior
</p>
</div>
<h1>Proposta de Solução</h1>
<p align=”Justify”>
	Criar um software onde seja possível o usuário administrador do sistema criar perfil de utilização da iluminação em uma residência e/ou comércio. Neste perfil o administrador consiga definir horários para acionamento e/ou não de uma(s) lâmpada(s) em um determinado cômodo do local.
	O perfil criado poderá estar associado a apenas um cômodo e/ou a toda a casa desde que todas as lâmpadas da residência e/ou comércio (lâmpadas que seja necessário o controle), estejam cadastradas no sistema e associada a seu respectivo cômodo do local gerenciado. 
	As lâmpadas terão em seu cadastro individual para controle do sistema o estado inicial e acionamento por interruptor, o estado inicial será utilizado quando por algum motivo o sistema seja reiniciado (queda de energia, reset manual do sistema, etc) e até que a comunicação do sistema com a lâmpadas sejam reestabelecidas novamente podendo permitir assim que os perfis cadastrados no sistema possam assumir o controle novamente das lâmpadas conforme configuração feita pelo administrador. Já o acionamento por interruptor, será utilizado quando a lâmpada em questão esteja associada a algum perfil cadastrado no sistema fazendo com que seja permitido ou não a alteração do estado da lâmpada via interruptor durante o período que aquele perfil esteja sendo utilizado.
	O sistema manterá o histórico de acionamentos das lâmpadas que estão sendo controladas: informando o tempo que esteve ligado, qual o consumo de energia durante aquele período e quantidade de acionamentos durante o dia.
No perfil cadastrado no sistema, poderá haver acionamentos (ligando ou desligado a lâmpada), por horários específicos, intervalo de horário, de acordo com a luminosidade do ambiente através de sensor de luminosidade e/ou através do interruptor.
	Como iremos fazer para controlar o acionamento das lâmpadas, armazenamento de dados e gerenciamento do sistema?
	Com auxílio de um microcontrolador de baixo custo identificado com o nome de ESP32 criado e desenvolvido por Espressif Sistemas, uma empresa Chinesa com sede em Xangai e é fabricado pela TSMC, este microcontrolador vem sendo mais utilizado no Brasil a partir de 2018 por apresentar entre suas características vários recursos e com um valor de mercado razoavelmente baixo. 
Entre os recursos do ESP32, está um processador dual core, WIFI, Bluetooth, até 18 canais de comunicação, sensor de temperatura, possibilidade de ligar um cartão micro SD, controlador remoto etc. a um custo de aproximadamente R$ 70,00. Este mesmo microcontrolador também pode ser utilizado como um hub para que sejam acoplados outros microcontroladores iguais ampliando assim ainda mais a quantidade de dispositivos controlados por ele.
A opção pela utilização até o momento por este microcontrolador foi devido a possibilidade de utilização de WIFI e Bluetooth sem precisar adicionar mais nada no microcontrolador e o baixo consumo de energia para execução de tarefas. Outro dispositivo que iremos utilizar, será o celular do próprio usuário para interação com o sistema e controle dos dispositivos (neste primeiro momento apenas lâmpadas). A comunicação entre usuário e as lâmpadas de sua residência/comércio, necessitará apenas do investimento no microcontrolador já que o celular, conforme pesquisa feita pela Fundação Getúlio Vargas (FGV) com os dados do IBGE de 2017, mostram que o Brasil em abril de 2018 já possuía 220 milhões de celulares em funcionamento e se fossemos levar em consideração todos os dispositivos móveis, já seriam mais de 306 milhões de equipamentos. A comunicação entre celular e o microcontrolador seria feita através do WIFI já que segundo a PNAD (Pesquisa Nacional por Amostra de Domicílios), em uma pesquisa em 2018 disponível no site do IBGE, já tínhamos 75,9% dos domicílios do Brasil com internet de banda larga fixa o qual sabemos também que grande parte da internet fixa, acompanham também o WIFI para distribuição da internet nos dispositivos moveis daquela residência não sendo este um custo para execução do projeto.
O sistema poderá emitir ou não mensagens aos celulares quando alguma luz for acesa bastando para isto estarem conectados na mesma rede WIFI do controlador e a mensagem deverá informas a luz que foi acesa e em qual cômodo.
O sistema já terá dois perfis cadastrados Diurno e Noturno e ambos em horários que não conflitam bastando ao usuário do sistema apenas associar as lâmpadas a cada um deles e/ou criar um outro perfil no sistema.
Existem outros equipamentos que permitem controlar lâmpadas via WIFI como Sonoff este equipamento possui um software com característica parecidas, porém, não encontrei nada entre suas característica onde fosse permitido criar um perfil para associar mais de uma lâmpada com a mesma regra e além disto seria necessário a compra de uma equipamento para cada lâmpada ou dispositivos com 4 saídas ou 8 saídas tornando assim inviável visto que o ESP32 permite a conexão com até 18 dispositivos no mesmo controlador.
</p>
<h1>Referências</h1>

Consumo Nacional de Energia elétrica feito pela EMPRESA DE PESQUISA ENERGÉTICA – EPE
	https://www.epe.gov.br/pt/publicacoes-dados-abertos/publicacoes/Consumo-Anual-de-Energia-Eletrica-por-classe-nacional
Pesquisa em 2018 disponível no site do IBGE PNAD (Pesquisa Nacional por Amostra de Domicílios) – Quanto a utilização da internet fixa e móvel no Brasil
	https://agenciadenoticias.ibge.gov.br/agencia-sala-de-imprensa/2013-agencia-de-noticias/releases/27515-pnad-continua-tic-2018-internet-chega-a-79-1-dos-domicilios-do-pais
Analise  Laboratório de Eficiência Energética em Edificações (LabEEE), localizado na Universidade Federal de Santa Catarina – Utilização final da energia Elétrica em uma residência.
	(http://labeee.ufsc.br/node/480#:~:text=Observou%2Dse%20que%20o%20consumo,3%20kWh%2Fm%C3%AAs%20no%20inverno.)
Reportagem apresentada pela Canaltech sobre pesquisa feita pela Fundação Getúlio Vargas com dados do IBGE sobre quantidade de celulares e dispositivos móveis no Brasil.
	https://canaltech.com.br/produtos/brasil-ja-tem-mais-de-um-smartphone-ativo-por-habitante-112294/#:~:text=Os%20n%C3%BAmeros%20s%C3%A3o%20da%20Funda%C3%A7%C3%A3o,dados%20mais%20recentes%20do%20IBGE
Datasheet do microntrolador ESP32 – Espressif. 
	https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf
Empresa do dispositivo SONOOF
	https://sonoffbrasil.com.br

