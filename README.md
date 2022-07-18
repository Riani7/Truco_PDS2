# Truco_PDS2




# User Stories
+ Eu como jogador gostaria de pedir truco.
+ Eu como jogador gostaria de olhar as cartas da minha mão.
+ Eu como jogador recebo três cartas.
+ Eu como jogador gostaria de jogar uma carta.
+ Eu como  jogador, estando na minha vez, posso aumentar o valor da rodada de acordo com as regras.
+ Eu como jogador gostaria de desistir da partida. 



#Como compilar o código:
É necessário baixar todos os arquivos presentes nesse repositório em uma mesma pasta e fazer o seguinte comando no cmd ou terminal utilizado (ex Powershell):
Makerun e depois ./bin/main


TP PDS II: Truco Mineiro
Jogo de truco programado em C++ para Windows para a matéria de Programação e Desenvolvimento de Software II pelos alunos Bruno Riani Araujo(2021019432), Pedro Augusto Rodrigues Barbosa (2021091265), Matheus Nogueira Arruda (2022425841) e Marcelle Christine Aquino Silva (2021014546)do curso de Engenharia de Sistemas e Engenharia de Controle e Automação da UFMG.

#Sobre o jogo:

O jogo foi programado para ter o prompt de comando, ou o Windows PowerShell como sua HMI(Human Machine Interface.

O jogo foi construído com base nas regras do truco mineiro, adaptado para 2 jogadores:.
Dois humanos, em times diferentes.
Regras:
O truco mineiro utiliza um baralho para jogo sem as cartas oito, nove, dez e coringa, o que totaliza 40 cartas para o jogo. As quatro cartas de maior valor no truco mineiro se chamam manilhas e são, nessa ordem:

Quatro de paus, conhecida como zap.
Sete de copas.
Ás de Espadas, conhecida como espadilha.
Sete de Ouros.
Para as outras cartas a relação de valor é a seguinte:

3 todos os naipes
2 todos os naipes
Ás todos os naipes, exceto o de espadas que é manilha.
K todos os naipes.
J todos os naipes.
Q todos os naipes.
7 somente paus e espadas, o de copas e ouros são manilhas.
6 todos os naipes
5 todos os naipes
4 todos os naipes, exceto paus que é o zap.
Príncipios básicos:

+Rodada:
No início da partida o jogador deve digitar 1 para inicializar o game. Logo após isso, cada um dos dois jogadores recebem três cartas que compõem sua mão. Em seguida, o primeiro jogador deve escolher uma de suas cartas para jogar, essa carta será impressa na mesa. Depois que o primeiro jogador deposita uma carta na mesa seu adversário deve fazê-lo, após isso a rodada é finalizada. O jogador que jogou a carta de maior valor ganha a rodada. O jogador que ganhar duas rodadas leva a queda e recebe dois pontos.

+Jogo
Após o fim de uma rodada uma nova é iniciada e esse processo se repete até que alguém junte um total de 12 pontos. Quando alguém soma 12 pontos este jogador vence a mão e todos tem os pontos zerados.

+Queda
A cada dois jogos ganhos por alguém, marca-se uma queda  Isso faz com que zere-se todos os pontos do jogo.

+Empate
Em caso de empate por valor da carta, o naipe será usado como critério de desempate.
Sobre o código:
De forma a garantir um código mais limpo e versátil criamos nosso jogo com Orientação a Objetos, utilizando tanto classes da Standart Library do C++ (STL), quanto classes criadas por nós. As classes criadas por nós foram implementadas em arquivos diferentes do main sendo cada classe implementada em seu própio .h.






#Classes criadas:
Cartas:
Tad criado para armazenar os dados que compõem uma carta sendo eles seu valor e seu naipe.
Funções:
carta:
É o construtor, recebe um valor e um naipe como parâmetros e cria um carta usando-os.
Recebe: Int, 
Retorna: Nada
Get_naipe:
Retorna o naipe da carta.
Recebe: Nada
Retorna: String
Get_valor:
Retorna o valor da carta
Recebe: Nada
Retorna: char
Get_ponto;
Retorna o ponto da carta atrelado ao _valor e _naipe da carta. 
Recebe: Nada
Retorna: Int
Imprime_carta;
Imprime a carta, com seu nipe e valor.
Recebe: Nada
Retorna: Nada
class mesa
Tad criado para armazenar os dados que compõem o baralho, sua inicialização e distribuição
funções:
void cria_baralho(); inicializa as cartas do baralho e as distribui aleatoriamente em um vector;
void distribiu_cartas() didtribui 3 cartas para cada jogador

class jogador
Tad criado para armazenar os dados que compõem um jogador, sendo eles sua mão, as possíveis cartas que ele pode jogar e ações durante o jogo como pedir truco.
Funções:
 imprime_mao(); //imprime a mão do jogador
Recebe: int
retorna: Nada  
bool pede_truco(); // gera um pedido de truco
recebe: int
retorna: int
Carta joga_carta(); // retorna a carta escolhida pelo jogador
recebe: int
retorna: int
 int aumenta(); // retorna o novo valor da rodada
recebe: int
retorna: int

 void distribui();
recebe: ind
retorna: nada
 coloca_carta(Carta *c);
recebe: int
retorna: int
 retira_carta(int indice);
recebe int
retorna: nada
 int get_quant_cartas();
recebe: int
retorna: nada

class jogo
private:
  int _queda; 
numero de quedas ganhas pelo jogador 1
  int _queda_bot;
numero de quedas ganhas pelo jogador 2
  int _mao;
numero de maos ganhas pelo jogador 1
  int _mao_bot;
numero de maos ganhas pelo jogador 2
  int _rodada;
numero de rodadas ganhas pelo jogador 1
  int _rodada_bot;
numero de rodadas ganhas pelo jogador 2
  vector<Carta *> baralho;
Baralho de 40 cartas (sem 8, 9 e 10)
public:
jogo();//construtor
void imprime_mesa(Carta *c);// imprime mesa que tem uma carta
void imprime_mesa_vazia(); // imprime uma mesa vazia
void imprime_msg_jog1_ou_jog2(int da_vez); imprime de quem eh a vez
bool imprime_placar();
imprime o placar e retorna se o jogo deve continuar
void imprime_vez();
void imprime_jogada(Carta c);
bool imprime_ganhou_rodada(int g, int valor); // imprime quem ganhou e retorna o ganhador
void imprime_começo(); // imprime mensagem de boas vindas
void cria_baralho(); // 
void termina_jogo();
void jogada(Carta *c);
int compara_cartas(Carta *c1, Carta *c2); compara duas e retorna ganhador
