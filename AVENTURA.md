# MineBlock 4.1: Explorador

Uma campanha independente e compacta de blocos, inspirada no Minecraft. As receitas, alturas, inimigos, portais e regras de combate foram adaptados. Nao e o Minecraft oficial nem uma implementacao de todas as suas mecanicas.

## Revisao Explorador

- Inventario compacto: quatro espacos de armadura ao lado da previa 3D, mao secundaria, crafting 2 x 2, mochila de 27 espacos e barra rapida de 9.
- Pilha no cursor: clique pega/coloca, direito pega metade ou coloca uma unidade, Shift transfere e duplo clique reune itens compativeis. No celular, o botao de modo permite colocar uma unidade por toque.
- Ingredientes reais na grade pessoal, com consumo atomico ao recolher o resultado. Cursor e grade sao salvos; ao fechar, os itens voltam a mochila ou a reserva se nao houver espaco.
- Explorador autoral com cabelo, olhos, lenco, roupa de viagem e mochila. Tres paletas de traje, quatro tons de pele e armadura visivel. A previa acompanha o mouse e pode ser girada.
- Mao em primeira pessoa com manga, punho, animacao de troca, balanco de movimento, mineracao, combate, comida e bloqueio. Ferramentas e objetos tem espessura e compartilham modelos com os drops. A mao esquerda e o tamanho sao configuraveis.
- Nova pixel art propria para ferramentas, espadas, armaduras, barras e gemas. Icones de lajes e escadas mostram sua forma, em vez de um cubo inteiro.

## Inteligencia das criaturas

A IA e um sistema local de estados e navegacao, nao um modelo de linguagem conectado a internet. Os comportamentos incluem observar, vagar, investigar sons, perseguir, procurar, recuar, mirar, fugir, seguir comida, buscar sombra e tentar outra rota.

- Visao por cone e oclusao real de blocos; a ultima posicao vista fica na memoria por alguns segundos. Sons revelam o ponto do ruido, nao a posicao atual escondida do jogador. Agachar reduz a deteccao.
- Caminhos A* com heap, diagonais sem cortar cantos, volumes diferentes por mob, alturas parciais, teto, agua, lava, cactos e limites de queda. Buscas tem limite de nos e orcamento compartilhado por quadro.
- Caminhos invalidam quando o mundo muda. Criaturas bloqueadas tentam um ponto lateral e recalculam, em vez de perseguir indefinidamente uma rota obsoleta. Corpos proximos se separam para reduzir aglomeracoes.
- Zumbis alertam aliados com linha de visao e aproximam-se por pequenos angulos diferentes. Zumbis/esqueletos buscam abrigo do sol.
- Esqueletos recuam de jogadores proximos, deslocam-se lateralmente, preparam a mira e antecipam moderadamente a trajetoria. Nao atiram quando outra criatura bloqueia a linha de tiro.
- Blazes usam movimento aereo com colisao e rajadas de tres disparos com preparacao e recarga. Aranhas podem subir junto a paredes para alcancar caminhos elevados.
- Endermen exigem olhar sustentado para provocar agressao; teletransportes tem intervalo e destinos validados. Podem se esquivar de projeteis, sem se tornarem permanentemente invulneraveis.
- Creepers verificam distancia e linha de visao durante o pavio. Animais priorizam fuga e seguir trigo sobre vagar.
- O dragao anuncia suas fases, compromete-se com um destino de investida e faz pausas no centro para permitir ataques corpo a corpo.
- Posicao e vida de criaturas comuns sao preservadas em salvamentos e entre dimensoes. Pensamentos, rotas e animacoes sao recalculados ao carregar.

Em Opcoes > Interface, habilite Comportamento do mob na mira para inspecionar o estado atual. A IA continua limitada por simulacao local; nao promete reproduzir toda a IA do Minecraft.

## Correcoes desta revisao

Pilhas nao empilhaveis respeitam seu limite, inclusive ensopados. Transferir para o proprio inventario nao duplica itens. Itens com encantamentos ou durabilidade diferentes nao sao fundidos. Itens na grade/cursor nao somem ao fechar, salvar ou morrer. A coleta de loot usa modelos 3D com formas corretas. Testes de linha atravessam todos os voxels e respeitam obstaculos finos, como cercas. Colocar blocos dentro de criaturas e bloqueado. Explosoes consideram abrigo e tambem atingem mobs. O pavio da TNT e salvo e fica suspenso quando sua regiao descarrega. O inventario nao pode ser reaberto por teclado por cima da morte/vitoria. O modo economico limita a frequencia das buscas da IA.

## Novidades de Terras Vivas

- Fome de 20 pontos, saciedade, gasto de energia por esforco, alimentacao com animacao e regeneracao condicionada a comida.
- Quatro composicoes musicais originais com acompanhamento, reverberacao e controles de reproducao no menu e nas opcoes. A selecao automatica acompanha o ambiente.
- Quinze biomas e oito familias de arvores, com troncos, folhas, tabuas e mudas proprias. O Atlas da Jornada ajuda a encontrar biomas sem teletransporte.
- Crafting interativo 2 x 2 no inventario e 3 x 3 na mesa. O livro preenche a grade; tambem e possivel montar manualmente e espelhar ferramentas.
- Bau de 27 espacos, organizacao da mochila, busca sem acentos, arrastar itens, Shift + clique e transferencia de pilhas.
- Escadas orientadas pelo olhar, lajes superiores/inferiores, lajes duplas, caminhos feitos com pa e previa de construcao.

Crie um mundo novo para acessar os 15 biomas e os recursos naturais novos. Saves existentes conservam seu gerador anterior para nao mudar o terreno sob construcoes; continuam recebendo fome, musica, baus, crafting e melhorias de interface.

## Fome e alimentacao

A barra de fome tem 20 pontos, mostrados por 10 icones ao lado dos coracoes. A saciedade e consumida antes da fome. Correr, pular, minerar e lutar gastam energia; ficar parado ou com um menu aberto nao gasta.

Com 6 pontos ou menos, o jogador nao pode correr. Com 18 ou mais e Regeneracao natural ligada, recupera 1 ponto de vida a cada 4 segundos, fora de combate, consumindo energia. Sem alimento, o dano de fome para em 10 de vida no Facil e 1 no Normal; no Dificil pode matar. Pacifico recupera a alimentacao. Fome e regeneracao podem ser configuradas separadamente.

Use a comida selecionada ou o botao Comer no inventario. Comer leva cerca de 1,35 segundos; pausar, trocar o item ou receber dano cancela sem consumir. Comida repoe fome e saciedade, nao vida instantanea. Maca dourada concede regeneracao adicional. Ensopado devolve a tigela.

Arbustos maduros rendem 3 bagas ao usar e amadurecem novamente em 45 segundos. Arbustos replantados comecam sem frutos. Melancias da selva deixam fatias. Trigo vira pao na mesa; cogumelos com tigela viram ensopado; carnes cruas podem ser assadas na fornalha.

## Biomas e arvores

Os biomas novos sao Planicies, Floresta, Bosque de betulas, Taiga, Tundra nevada, Deserto, Savana, Selva, Manguezal, Bosque de cerejeiras, Terras aridas, Montanhas, Floresta escura, Praia e Oceano. A distribuicao depende da semente, altitude, temperatura e umidade.

As oito madeiras sao Carvalho, Betula, Pinheiro, Acacia, Selva, Carvalho escuro, Cerejeira e Mangue. Receitas comuns aceitam tabuas de especies diferentes. Folhas podem deixar mudas. Plantadas em solo adequado e com espaco, mudas crescem em aproximadamente 60 segundos de simulacao proxima; farinha de osso acelera o crescimento. A geracao considera arvores fora do chunk para manter copas completas nas bordas.

O Atlas pode marcar as coordenadas de um bioma em um raio de ate 1536 blocos. Nao garante encontrar todo bioma nessa area, especialmente em mapas legados ou planos. A bussola informa o destino marcado; a busca nao gera chunks nem teletransporta.

## Crafting e armazenamento

Na grade, escolha um ingrediente na mochila e toque em uma celula, ou arraste do inventario no PC. Toque novamente para remover. Escolher uma receita no livro preenche uma previa. Materiais sao consumidos apenas ao coletar o resultado; fechar a interface nao perde itens. A grade 2 x 2 nao aceita receitas de ferramentas que exigem a mesa 3 x 3. Fornalha, ferraria e encantamentos continuam em suas interfaces especificas.

Crie um bau com 8 tabuas em um anel 3 x 3. Toque nos itens para transferir. Guardar mochila preserva a barra rapida; Recolher tudo leva apenas o que cabe. A tampa precisa de espaco livre. Quebrar o bau derruba o conteudo e remove o registro salvo para impedir duplicacao.

Organizar junta pilhas e ordena apenas os 27 espacos da mochila. Durabilidade e encantamentos sao preservados. Shift + clique move entre mochila e barra rapida sem sobrescrever o destino. Lajes encaixadas uma na outra formam um bloco completo e deixam duas lajes ao quebrar.

## Comecar

Crie um mundo novo em Sobrevivencia. Os quatro tipos de terreno possuem madeira e recursos para a campanha. O botao Jornada, ou J no teclado, explica as nove etapas e mostra as alturas dos minerais. Criativo permite testar todos os itens e a batalha sem dano.

## Caminho ate o final

1. Quebre madeira, crie tabuas, gravetos e a mesa de trabalho.
2. Crie picaretas de madeira e pedra. Extraia carvao e ferro bruto.
3. Monte a fornalha com 8 pedregulhos e funda os metais. Crie espada, escudo e armadura.
4. Extraia diamantes entre Y 4 e 18 usando ferro. Com a picareta de diamante, extraia obsidiana abaixo de Y 9.
5. Crie a pederneira com silex + ferro. Construa uma moldura vertical 4 x 5 de obsidiana, com interior vazio 2 x 3. Os cantos sao opcionais, totalizando 10 blocos. Acenda a base interna e entre no campo roxo.
6. No Nether, derrote blazes para obter varas. Na superficie, derrote sombras para obter perolas. Cada vara cria 2 pos; po + perola cria um olho.
7. Crie 12 molduras do Fim na mesa. Monte um anel horizontal 5 x 5 sem os cantos, deixando o centro 3 x 3 vazio. Insira 12 olhos, um por moldura. Entre no centro ativado. A orientacao das molduras foi simplificada nesta edicao.
8. Destrua os quatro cristais nas torres baixas. O dragao e invulneravel enquanto algum cristal estiver ativo.
9. Ataque com flechas durante o voo e com espada nas investidas. Bloqueie o fogo com escudo e coma para recuperar vida. A vitoria entrega um trofeu, salva a conclusao e permite continuar no mundo.

O portal de chegada oferece retorno a superficie. Saia do campo do portal antes de atravessar novamente, evitando loops de teletransporte. Vida do chefe e cristais destruidos persistem ao salvar, sair ou morrer. Criaturas comuns proximas sao salvas com posicao e vida. Na morte, a regra "Manter itens" decide se o equipamento e preservado ou deixado no chao. Configuracoes antigas preservam a regra anterior.

## Equipamentos

- Picareta, machado, pa, enxada e espada em madeira, pedra, cobre, ferro, ouro, diamante e netherita.
- Capacete, peitoral, calcas e botas em couro, malha, cobre, ferro, ouro, diamante e netherita.
- Arco, besta, flechas, tridente, maca, escudo, pederneira, bussola e luneta.
- Equipamentos tem durabilidade, velocidade/dano/protecao e encantamentos ate III.
- O escudo protege pela frente quando levantado. Armadura nao reduz dano de queda.
- O oxigenio diminui debaixo d'agua. Sem ar, o jogador sofre dano de afogamento; volte a superficie para recuperar as bolhas.
- O tridente sai da mao ao ser lancado e pode ser recolhido depois. Flechas que atingem blocos podem ser recuperadas.
- A enxada ara a terra. Sementes viram trigo em 30 segundos de jogo ativo; trigo vira pao na mesa.
- Esmeralda vira pao na mesa; esmeralda e la branca viram linha. Estas trocas sao receitas adaptadas desta edicao.

## Minerais e estacoes

Carvao, cobre, ferro, ouro, redstone, lapis-lazuli, diamante e esmeralda aparecem na superficie; seus oito minerios tambem possuem variantes de ardosia. Quartzo, ouro do Nether e detritos ancestrais aparecem no Nether. Ametista e encontrada em cristais subterraneos.

A fornalha faz a fusao simplificada dos metais e dos detritos. Na ferraria, 4 fragmentos + 4 barras de ouro criam netherita. Equipamento de diamante + barra de netherita + molde de melhoria cria a versao de netherita e preserva encantamentos. O molde e uma receita adaptada de diamante, netherrack e ametista.

A mesa de encantamentos consome 3 lapis-lazuli, 1 ametista e 5 XP por nivel. Restaura a durabilidade e melhora combate, mineracao ou protecao.

## Controles

- PC: WASD, mouse, Espaco para pular, E para inventario/estacao, J para jornada, R para escudo, 1-9 para selecionar item.
- Clique esquerdo ataca ou minera. Direito usa um item, coloca um bloco ou abre uma estacao.
- Q solta um item; Ctrl + Q solta a pilha. G faz a coleta manual. Shift agacha e evita cair das bordas.
- Se a captura de mouse for bloqueada pelo navegador: arraste para olhar, segure Z para atacar/minerar e use V para colocar/usar.
- Celular: joystick, arraste para olhar e botoes ATACAR/MINAR, USAR, DEFENDER, AGACHAR e pulo. SOLTAR deixa o item no chao; o inventario tambem permite soltar pilhas e dividi-las. Jornada abre o guia.

## Saves

O formato v4 salva mundos modificados, tres regioes, inventario, equipamentos, fome/saciedade, durabilidade, encantamentos, cultivos, mudas, baus, orientacoes de blocos, itens no chao, estruturas de portais e progresso. A versao do gerador tambem e mantida. IDs existentes nao foram reutilizados. Ha receitas para aproveitar minerios antigos. Portais antigos de bloco unico podem ser convertidos em estruturas se houver espaco livre.

O crafting e atomico: se o resultado nao cabe, nao consome ingredientes. Mineracao e criaturas deixam loot no chao; uma mochila cheia nao apaga esses itens. A Reserva ainda preserva excedentes de recompensas e itens acima do limite de entidades. Nao apague os dados do navegador se quiser manter seus mundos.

No menu de pausa, "Exportar copia do mundo" baixa um JSON. Em Selecionar Mundo, "Importar copia" valida o arquivo e cria outro mundo, sem sobrescrever o original. Falha ao salvar impede a saida automatica para evitar perder alteracoes.

## Texturas, criaturas e sons

- Terreno, minerios, madeira e molduras redesenhados em pixel art propria, em 8x, 16x, 32x e 64x.
- Agua, lava e portais animados; mipmap e filtragem anisotropica opcionais. Folhas rapidas ficam opacas e removem faces internas.
- Zumbis, esqueletos, aranhas, creepers, endermen, blazes, vacas, porcos e dragao com modelos de blocos proprios.
- Percepcao por linha de visao, memoria curta, caminhos locais A* limitados, desvio de obstaculos, recuo de atiradores e fuga de animais.
- Zumbis/esqueletos queimam sob ceu aberto durante o dia; aranhas sao neutras de dia; endermen reagem ao olhar e teletransportam; creepers cancelam o pavio se o jogador se afasta.
- Animais seguem trigo e deixam carne crua. Use a fornalha para cozinhar.
- Sons sintetizados proprios por material, combate, criaturas, portais, inventario e ambiente. Quatro trilhas originais: Primeiro Amanhecer, Entre as Copas, Constelacoes e Alem da Pedra. A musica usa melodia, arpejos, baixo e reverberacao. O navegador exige uma interacao para liberar audio.

## Desempenho

As opcoes incluem resolucao adaptativa, meta de FPS, limite de quadros, distancia de simulacao, limite de criaturas, densidade de particulas, orcamento de chunks e predefinicoes. A simulacao congela longe do jogador; itens param de envelhecer nessas regioes. Os menus em pausa reduzem a renderizacao do mundo a 15 FPS. Nao ha garantia de FPS para todo aparelho.

Itens no chao duram 300 segundos de simulacao proxima. Ha mesclagem de pilhas e um limite de entidades. Lava destroi itens comuns; o vazio destroi os drops. Durabilidade e encantamentos sao preservados. Colisoes de lajes, escadas, cercas e molduras seguem as formas visuais. Areia/cascalho caem apos perderem o suporte; plantas e tochas sem apoio soltam itens.

## Verificacao

O build web pode ser verificado com `npm run build`.

Os testes em `tests/adventure.test.ts`, `tests/classic.test.ts`, `tests/living.test.ts` e `tests/explorer.test.ts` cobrem catalogo, fome, biomas, crafting, cursor, conservacao de itens, backups, persistencia de criaturas, escolhas da IA, navegacao por volume, diagonais e oclusao em cercas. Para executa-los em um ambiente com terminal: `npx --yes --package=tsx tsx --test tests/*.test.ts`.

Checklist manual: criar mundo, obter ferramenta, abrir mesa, fundir ferro, equipar armadura, defender, soltar/coletar itens, testar mochila cheia e morte, lancar/recolher tridente, plantar/colher, construir/ativar/destruir os dois portais, destruir cristais, vencer, salvar/reabrir e exportar/importar. Verificar celular na vertical/horizontal, volumes, legendas e a predefinicao Rapido.

A compilacao web nao substitui testes de uma partida inteira em um aparelho real. As receitas e o clima sao adaptacoes, nao copias completas das regras e conteudos do Minecraft.