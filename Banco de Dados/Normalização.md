# Normalização

## Primeira Forma Normal (1FN)
- Nesta forma, cada tabela **deve ter uma chave primária única**, que identifica cada registro;
- Além disso, cada atributo deve ser indivisível e mínimo. Não devem haver grupos repetidos de dados, nem valores múltiplos em uma mesma coluna.

## Segunda Forma Normal (2FN)

- Nesta forma, além de seguir a 1FN, cada tabela deve eliminar as dependências parciais;
- Isso significa que todos os campos não primários devem depender totalmente da chave primária.

## Terceira Forma Normal (3FN)

- Nesta forma, além de seguir a 2FN, cada tabela deve eliminar as dependências transitivas.
- Isso significa que nenhum campo não primário deve depender de outro campo não primário.
