# Testes

- Caixa Preta
  - Mais geral;
  - Baseado nos casos de uso
  - Verifica se os objetos e o sistema funcionam conforme o esperado;
  - Dada uma entrada conhecida, verifica se a saída correta é obtida;
  - Atinge de 34% a 50% do código.
- Caixa Branca
  - Mais específico;
  - Se baseia unicamente na implementação de um método;
  - Tendem a atingir 100% do código;

## Formas de teste

### Teste de unidade

- Examina **apenas um recurso por vez**;
- Envia uma mensagem para o objeto e verifica se recebeo resultado esperado;
- É o nível mais baixo dos testes.

### Teste de integração

- Verifica se os objetos que compõem o sistema **interagem corretamente**;
- Nem tudo aquilo que funciona isoladamente vai trabalhar corretamente em conjunto.

### Teste de regressão

- Examina as alterações nas partes do sistema **que já foram validadas**;
- Após qualquer alteração feita, essa parte modificada e todas as partes dependentes devem ser testadas novamente;
- Qualquer pequena alteração pode ter inserido novos erros ao sistema;
- Para executar um teste de regressão, basta executar novamente todos os outros testes.
