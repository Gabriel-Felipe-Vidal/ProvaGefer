# Prova
## Materia: Estrutura de Classificação de Dados
## Professor: Geferson Luis Simonete
## Aluno: Gabriel Felipe Vidal


### O algoritmo mais eficiente na ordenação de dados é o Quick Sort

#### Ordenação de dados – conceito
##### Ordenação é o ato de colocar os elementos de uma sequência de informações, ou dados, em uma ordem predefinida.O termo técnico em inglês para ordenação é sorting, cuja tradução literal é “classificação”. Os algoritmos que ordenam um conjunto, geralmente representados em um vetor, são chamados de algoritmos de ordenação.
##

#### Insertion Sort
##### Insertion Sort, ou ordenação por inserção, é um algoritmo de ordenação que, dado uma estrutura constrói uma matriz final com um elemento de cada vez, uma inserção por vez. Assim como algoritmos de ordenação quadrática, é bastante eficiente para problemas com pequenas entradas, sendo o mais eficiente entre os algoritmos desta ordem de classificação.


    public static void main(String[] args) throws IOException {
    int quantidade = 10000;
    int[] vetor = new int[quantidade];

    for (int i = 0; i < vetor.length; i++) {
     vetor[i] = (int) (Math.random()*quantidade);
    }

     long tempoInicial = System.currentTimeMillis();

     insertionSort(vetor);

     long tempoFinal = System.currentTimeMillis();

     System.out.println("Executado em = " + (tempoFinal - tempoInicial) + " ms");

    }

     public static void insertionSort(int[] vetor) {
    int j;
    int key;
    int i;

    for (j = 1; j < vetor.length; j++)
    {
      key = vetor[j];
      for (i = j - 1; (i >= 0) && (vetor[i] > key); i--)
      {
         vetor[i + 1] = vetor[i];
       }
        vetor[i + 1] = key;
        
        











#### Bubble Sort
##### O bubble sort, ou ordenação por flutuação (literalmente “por bolha”), é um algoritmo de ordenação dos mais simples. A ideia é percorrer o vetor diversas vezes, ea cada passagem fazer flutuar para o topo o maior elemento da sequência. Essa movimentação lembra uma forma como bolhas em um tanque de água procuram seu próprio nível, e disso vem o nome do algoritmo.
    public static void main(String args[]){
	int[] vet = {8, 9, 3, 5, 1};
	int aux = 0;
	int i = 0;

	System.out.println("Vetor desordenado: ");
	for(i = 0; i<5; i++){
		System.out.println(" "+vet[i]);
	}
	System.out.println(" ");

	for(i = 0; i<5; i++){
		for(int j = 0; j<4; j++){
			if(vet[j] > vet[j + 1]){
				aux = vet[j];
				vet[j] = vet[j+1];
				vet[j+1] = aux;
			}
		}
	}
	System.out.println("Vetor organizado:");
	for(i = 0; i<5; i++){
		System.out.println(" "+vet[i]);}
 
#### Selection Sort
##### A ordenação por seleção (do inglês, selection sort) é um algoritmo de ordenação baseado em se passar sempre o menor valor do vetor para a primeira posição (ou o maior dependendo da ordem requerida), depois o de segundo menor valor para a segunda posição, e assim é feito sucessivamente com os  elementos restantes, até os últimos dois elementos.
#
    public class OrdenacaoSelecao {
    public static void main(String[] args) {
        // valores a serem ordenados
        int vetor[] = {7,3,9,1,10};
        // armazenam o menor valor e o índice do menor valor
        int menor, indiceMenor;

        for (int i = 0; i < vetor.length - 1; i++) {
            // antes de comparar, considera-se menor o valor atual do loop
            menor = vetor[i];
            indiceMenor = i;

            // compara com os outros valores do vetor
            for (int j = i + 1; j < vetor.length; j++){
                if (vetor[j] < menor){
                    menor = vetor[j];
                    indiceMenor = j;
                }
            }

            // troca os valores menor e maior
            vetor[indiceMenor] = vetor[i];
            vetor[i] = menor;
        }

        // exibe os números na tela
        String numerosOrdenados = "";
        for (int n : vetor) {
            numerosOrdenados += n+"-";
        }
        JOptionPane.showMessageDialog(null,numerosOrdenados);
    }
    }


#### Quick Sort
##### O algoritmo quicksort é um método de ordenação muito rápido e eficiente, inventado por C.A.R. Ele criou o quicksort ao tentar traduzir um dicionário de inglês para russo, ordenando as palavras, tendo como objetivo reduzir o problema original em subproblemas que possam ser resolvidos mais fácil e rápido.
#
    public static void main(String[] args) throws IOException {
             int quantidade = 10000;
             int[] vetor = new int[quantidade];

             for (int i = 0; i < vetor.length; i++) {
                     vetor[i] = (int) (Math.random()*quantidade);             }

             long tempoInicial = System.currentTimeMillis();

             quickSort(vetor,0,vetor.length-1);

             long tempoFinal = System.currentTimeMillis();

             System.out.println("Executado em = " + (tempoFinal - tempoInicial) + " ms");      }

       private static void quickSort(int[] vetor, int inicio, int fim) {
             if (inicio < fim) {
                    int posicaoPivo = separar(vetor, inicio, fim);
                    quickSort(vetor, inicio, posicaoPivo - 1);
                    quickSort(vetor, posicaoPivo + 1, fim)   }       }

       private static int separar(int[] vetor, int inicio, int fim) {
             int pivo = vetor[inicio];
             int i = inicio + 1, f = fim;
             while (i <= f) {
                    if (vetor[i] <= pivo)
                           i++;
                    else if (pivo < vetor[f])
                           f--;
                    else {
                           int troca = vetor[i];
                           vetor[i] = vetor[f];
                           vetor[f] = troca;
                           i++;
                           f--;                   }             }
             vetor[inicio] = vetor[f];
             vetor[f] = pivo;
             return f;
       }
    }
    }


## Arvore Binária
##### É uma estrutura de dados caracterizada por: Ou não tem elemento algum (árvore vazia). Ou tem um elemento distinto, denominado raiz, com dois apontamentos para duas estruturas diferentes, denominadas sub-árvore esquerda e sub-árvore direita. Perceba que a definição é recursiva e, devido a isso, muitas operações sobre árvores binárias utilizam recursão. É o tipo de árvore mais utilizado na computação. A principal utilização de árvores binárias são as árvores de busca.
####
##### Um nó de uma árvore binária é composto por, pelo menos, três elementos, a sua chave e mais dois ponteiros que apontam um para a sub-árvore esquerda e outro para a sub-árvore direita.
#### Exemplo de codigo para organização de arvore
     class No 
    {
    private:

    int chave;    
   
    No *esq;
    No *dir;
    

    No ( int chave )
    {
        this->chave = chave;    // seta a chave
        esq = nullptr;          // inicializa a sub-arvore esquerda como null.
        dir = nullptr;          // inicializa a sub-arvore direita como null.
    }
    int getChave()
    {
        return chave;    
    }  
    No* getEsq()
    {
        return esq;
    }
    
    No* getDir()
    {
        return dir;
    }
    void setEsq( No* esq )
    {
        this->esq = esq;
    }  
    void setDir( No* dir )
    {
        this->dir = dir;
    }
    };
    

## Arvore Binária Balanceada

##### Uma árvore balanceada são as árvores que minimizam o número de comparações efetuadas no pior caso para uma busca com chaves de probabilidades de ocorrências idênticas.
##### Estas estruturas fornecem implementações eficientes para listas ordenadas mutáveis, podendo ser usadas para outras estruturas de dados abstratas, tais como arrays associativos, filas de prioridade e conjuntos.
## Arvore Binária Não Balanceada
##### Basicamente é qualquer arvore que não atinja o menor tempo de calculo possivel.




