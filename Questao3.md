Programa compilado com no Ubuntu 14.04 TLS  
Comando para compilação:   
gcc -pthread primos.c -o primos.out  
./primos.out
~~~~
#include<stdio.h>
#include<pthread.h>
 
#define INTERVALO 100000                   //0 a 99999
#define CONJUNTO 1000                      //conjuntos de 1000 elementos dentro do intervalor
#define NUM_THREADS INTERVALO/CONJUNTO     //1 thread para cada conjunto

int nthread = 1;

void *threadPrimos(){
    if(nthread*CONJUNTO > INTERVALO){
        return;
    }
    
    int i,j,count;
    
    int inicio = (nthread-1)*CONJUNTO;
    int fim = (nthread*CONJUNTO);


    for(i = inicio; i < fim; i++) {
        if(i == 2) {
            printf("%d ", i);
        } else if(i%2 != 0) {
            for (j = 1; j < fim; j++) {
                if(i%j ==0)
                    count++;
            }
            if(count <= 2)
                printf("%d ", i);
            count = 0;
        }
    }
    printf("\n");
    nthread++;
}

void main(){
    pthread_t thread[NUM_THREADS];
    int i;
    
    for(i=0; i<NUM_THREADS ; i++){
        pthread_create(&thread[i], NULL, threadPrimos, NULL);
    }
    
    for(i=0;i< NUM_THREADS;i++){
        pthread_join(thread[i],NULL);
    }
}
~~~~
