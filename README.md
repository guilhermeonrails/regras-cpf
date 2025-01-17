# Regras para um CPF Válido

## Estrutura do CPF

O CPF é um número formado por 11 dígitos decimais com a seguinte configuração: ABC.DEF.GHI-JK

**Exemplo de CPF**: `123.456.789-09`.

Os oito primeiros dígitos são formados por um número base definido pela Receita Federal.  
O 9º número, ocupado pela letra I, informa o estado em que o CPF foi emitido, conforme mostra a tabela abaixo:

| Região Fiscal | Estados                                  | Nono Dígito |
|----------------|------------------------------------------|-------------|
| 1.ª            | DF, GO, MT, MS, TO                      | 1           |
| 2.ª            | AC, AP, AM, PA, RO, RR                  | 2           |
| 3.ª            | CE, MA, PI                              | 3           |
| 4.ª            | AL, PB, PE, RN                          | 4           |
| 5.ª            | BA, SE                                   | 5           |
| 6.ª            | MG                                       | 6           |
| 7.ª            | ES, RJ                                   | 7           |
| 8.ª            | SP                                       | 8           |
| 9.ª            | PR, SC                                   | 9           |
| 10.ª           | RS                                       | 0           |


## Validação de CPF

O CPF é válido se os **dois últimos dígitos** (dígitos verificadores) forem calculados corretamente a partir dos 9 primeiros dígitos.

## Condições para um CPF ser Inválido

O CPF será considerado **inválido** nas seguintes situações:
- O CPF não pode ter números repetidos em sequência, como: `111.111.111-11`.
- Os **dígitos verificadores** precisam ser calculados corretamente. Caso contrário, o CPF será inválido.

---

## Cálculo dos Dígitos Verificadores

### Cálculo do 1º Dígito Verificador

1. Multiplicar os 9 primeiros números do CPF pelos seguintes pesos: `[10, 9, 8, 7, 6, 5, 4, 3, 2]`.
2. Somar os resultados dessas multiplicações.
3. Calcular o resto da soma dividida por 11.
4. Se o resto for menor que 2, o 1º dígito é **0**. Caso contrário, o 1º dígito é `11 - resto`.

### Cálculo do 2º Dígito Verificador

1. Multiplicar os 9 primeiros números do CPF mais o 1º dígito verificador pelos seguintes pesos: `[11, 10, 9, 8, 7, 6, 5, 4, 3, 2]`.
2. Somar os resultados dessas multiplicações.
3. Calcular o resto da soma dividida por 11.
4. Se o resto for menor que 2, o 2º dígito é **0**. Caso contrário, o 2º dígito é `11 - resto`.

---

## Exemplo de Cálculo

**CPF**: `123.456.789-09`

### 1º Dígito Verificador:
1. **Multiplicação**:  
   \( 1 \times 10 + 2 \times 9 + 3 \times 8 + 4 \times 7 + 5 \times 6 + 6 \times 5 + 7 \times 4 + 8 \times 3 + 9 \times 2 \)
   \[
   = 10 + 18 + 24 + 28 + 30 + 30 + 28 + 24 + 18 = 210
   \]

2. **Resto** da divisão de \( 210 \) por \( 11 \):  
   \[
   210 \mod 11 = 1
   \]

3. **Regra do dígito**:  
   - Se o resto for menor que 2, o dígito é **0**.  
   - Como o resto é \( 1 \), o 1º dígito é **0**.

---

### 2º Dígito Verificador:
1. **Multiplicação**:  
   Agora usamos os 9 números do CPF mais o 1º dígito (0):  
   \( 1 \times 11 + 2 \times 10 + 3 \times 9 + 4 \times 8 + 5 \times 7 + 6 \times 6 + 7 \times 5 + 8 \times 4 + 9 \times 3 + 0 \times 2 \)  
   \[
   = 11 + 20 + 27 + 32 + 35 + 36 + 35 + 32 + 27 + 0 = 260
   \]

2. **Resto** da divisão de \( 260 \) por \( 11 \):  
   \[
   260 \mod 11 = 7
   \]

3. **Regra do dígito**:  
   - Se o resto for menor que 2, o dígito é **0**.  
   - Caso contrário, o dígito é \( 11 - \text{resto} \).  
   - \( 11 - 7 = 4 \), então o 2º dígito é **4**.

---

### Resultado final:
O CPF corrigido seria **123.456.789-04**, e ele é **válido**.

---

## Conclusão
Agora o markdown está com os **valores corrigidos** e mais claro para quem quiser aprender!
