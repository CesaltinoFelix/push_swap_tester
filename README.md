# Lista já ordenada
./push_swap 1 2 3

# Lista invertida
./push_swap 3 2 1

# Lista com 5 elementos aleatórios
./push_swap 2 5 1 4 3

# Lista com números negativos
./push_swap -3 -1 -2 -5 0



############################################




# Lista de 20 números
./push_swap $(seq 20 | shuf)

# Lista com mistura de positivos e negativos
./push_swap $(shuf -i -50:50 -n 20)



##############################

# 100 números aleatórios
./push_swap $(seq 100 | shuf) | wc -l

# 500 números aleatórios
./push_swap $(seq 500 | shuf) | wc -l



###################################


# Apenas um número
./push_swap 42

# Dois números
./push_swap 2 1

# Números repetidos (deve dar erro)
./push_swap 1 2 3 2

# Valor máximo e mínimo de int
./push_swap -2147483648 0 2147483647

# Sequência já ordenada mas grande
./push_swap $(seq 500)

# Sequência inversa grande
./push_swap $(seq 500 | sort -nr)


###################################

#!/bin/bash
for i in {1..50}
do
    ARG=$(shuf -i 0:1000 -n 100)
    ./push_swap $ARG | ./checker_linux $ARG
done

