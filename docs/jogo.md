# Street Kings

## 1. Tema e objetivo

Street Kings passa-se numa cidade onde as corridas de rua ilegais decidem quem manda. O jogador é um piloto novato que começa com um carro simples e 300 moedas. Para progredir, corre contra pilotos rivais, aceita missões, compra peças e consumíveis na loja e repara o carro. Cada vitória dá dinheiro e experiência (XP), que fazem o piloto subir de nível. Fica em 1.º lugar do ranking quem tiver o nível mais alto, e em caso de empate mais XP e mais vitórias.

**Correspondência com os termos do enunciado:**

| Enunciado | No jogo |
|-----------|---------|
| Personagem | Piloto (e o seu carro) |
| Vida | Integridade do carro |
| Energia | Combustível |
| Ataque | Velocidade |
| Defesa | Aderência |
| Combate | Corrida |
| Adversário | Rival |

## 2. Classes de personagem

| Classe | Integridade | Velocidade | Aderência | Combustível |
|-------------|-------------|------------|-----------|-------------|
| Velocista | 80 | 18 | 4 | 100 |
| Resistente | 120 | 12 | 8 | 100 |
| Equilibrado | 100 | 14 | 6 | 100 |

- Dinheiro inicial: **300 moedas**.
- Nível inicial: 1. XP inicial: 0.
- O combustível máximo é sempre 100.

## 3. Experiência e níveis

- XP necessária para passar ao nível seguinte: **100 × nível atual** (nível 1 → 2 precisa de 100 XP; nível 2 → 3 precisa de 200 XP).
- O XP guardado é o total acumulado desse nível; ao subir, o XP gasto é descontado (ex.: 130 XP no nível 1 passa a 30 XP no nível 2).
- Ao subir de nível: **+10 integridade máxima, +2 velocidade, +1 aderência**, a integridade fica no máximo e o combustível fica a 100.
- Nível máximo: 10.
- Formas de ganhar XP: corridas e missões.
- Se ganhar XP suficiente para subir mais do que um nível de uma vez, sobe todos os níveis seguidos.

## 4. Itens da loja

| Nome | Tipo | Preço | Stock | Efeito |
|-------------------|-------------|-------|-------|-------------------------------------------|
| Kit de Reparação | consumível | 50 | 100 | recupera 40 de integridade |
| Bidão de Combustível | consumível | 40 | 100 | recupera 50 de combustível |
| Nitro | consumível | 80 | 50 | +6 velocidade na próxima corrida |
| Motor Turbo | peça | 200 | 15 | +4 velocidade |
| Pneus Desportivos | peça | 150 | 20 | +3 aderência |
| Blindagem | peça | 180 | 15 | +20 integridade máxima |
| Pintura Rara | especial | 500 | 3 | sem efeito (troféu de coleção) |

**Regras:**
- Regra de venda: a loja compra por **50% do preço** (arredondado para baixo). Um item vendido volta ao stock da loja.
- Não se pode comprar sem dinheiro suficiente nem quando o stock é 0.
- Só se pode vender o que está no inventário.
- **Peças** ficam instaladas no carro assim que são compradas e os seus bónus somam-se aos atributos enquanto estiverem no inventário. Só se pode ter **1 de cada peça**. Se for vendida, o bónus desaparece.
- **Itens que se podem "usar":** Kit de Reparação, Bidão de Combustível e Nitro. Ao usar, o item gasta-se (quantidade −1).
- A integridade e o combustível nunca ultrapassam o máximo.
- O Nitro só dura uma corrida; se o jogador não correr, fica ativo até à próxima corrida. Só pode ter 1 Nitro ativo de cada vez.
- A Pintura Rara não se usa, só se coleciona ou vende.

## 5. Adversários

| Nome | Nível | Integridade | Velocidade | Aderência | Dinheiro | XP | Prob. nitro (crítico) | Prob. desistir (fuga) |
|----------------|-------|-------------|------------|-----------|----------|-----|------------------------|------------------------|
| Tiago Novato | 1 | 40 | 8 | 3 | 30 | 40 | 5% | 10% |
| Marta Drift | 2 | 70 | 12 | 5 | 60 | 70 | 8% | 10% |
| Rui Turbo | 3 | 110 | 17 | 8 | 100 | 110 | 10% | 8% |
| Sara Nitro | 4 | 150 | 22 | 11 | 150 | 160 | 12% | 5% |
| Rei da Noite | 5 | 200 | 30 | 14 | 250 | 250 | 15% | 0% |

## 6. Regras de corrida

Uma corrida é jogada por rondas, como um combate por turnos.

1. **Condições para correr:** combustível ≥ 20 e integridade ≥ 20. Caso contrário o jogo recusa a corrida e sugere usar um Bidão ou um Kit de Reparação.
2. **Gasto de combustível:** cada corrida gasta **20 de combustível**, descontados no início. O combustível recupera +20 sempre que o jogador inicia sessão (até 100).
3. **Quem ataca primeiro:** o jogador.
4. **Cálculo do dano:** `dano = velocidade do atacante − aderência do defensor`. O dano mínimo é 1. A velocidade e a aderência do jogador incluem os bónus das peças e do Nitro.
5. **Sorte:**
   - O dano é multiplicado por um valor aleatório entre **0,8 e 1,2** (arredondado, mínimo 1).
   - O rival tem a probabilidade de nitro da tabela: se sair, o dano dessa ronda **×1,5**. O jogador tem **5%** de probabilidade de nitro (×1,5).
   - No início de cada ronda do rival, se a integridade dele estiver abaixo de 25%, existe a probabilidade de desistir da tabela.
6. **Fim da corrida:**
   - O jogador **vence** se a integridade do rival chegar a 0.
   - O jogador **perde** se a sua integridade chegar a 0.
   - Se o rival **desiste**, a corrida termina sem vencedor.
7. **Recompensas:**

| Resultado | Dinheiro | XP | Outras |
|-----------|----------|----|--------|
| Vitória | dinheiro do rival | XP do rival | +1 vitória |
| Derrota | perde 10% do dinheiro (arredondado para baixo) | +10 XP | +1 derrota, integridade fica a 1 se chegou a 0 |
| Rival desiste | 0 | 50% do XP do rival | sem vitória nem derrota |

- A integridade que sobra após a corrida mantém-se (o carro fica danificado até ser reparado).
- O Nitro ativo é consumido em qualquer resultado.
- Todas as corridas são registadas no histórico.

## 7. Missões

| Nome | Objetivo | Dificuldade | Dinheiro | XP |
|---------------------|----------------------------------|-------------|----------|-----|
| Primeira Corrida | Vencer 1 rival | fácil | 50 | 40 |
| Rua Limpa | Vencer 3 rivais | fácil | 100 | 80 |
| Mecânico | Comprar 2 peças na loja | fácil | 80 | 60 |
| Cliente Fiel | Gastar 300 moedas na loja | média | 120 | 100 |
| Caçador de Lendas | Vencer o Rui Turbo | média | 200 | 150 |
| Rei da Estrada | Vencer o Rei da Noite | difícil | 400 | 300 |

**Estados de uma missão:** Disponível, Em curso, Concluída, Falhada.

- Uma missão está **Disponível** até o jogador a aceitar. Passa a **Em curso** ao aceitar.
- O progresso só conta a partir do momento em que a missão é aceite.
- **Quando falha:** as missões de corrida falham se o jogador **perder 3 corridas** enquanto a missão está em curso. As missões de loja não falham.
- Uma missão falhada volta a ficar Disponível se o jogador a quiser aceitar de novo (o progresso volta a 0).
- Uma missão concluída não se repete.
- Quantas missões pode ter em curso ao mesmo tempo: **2**.
- A recompensa é dada automaticamente ao concluir.

## 8. Ranking

Critério de ordenação (por ordem de desempate):

1. Nível (maior primeiro)
2. XP (maior primeiro)
3. Vitórias (maior primeiro)

O jogador consulta a sua posição e a lista dos 10 melhores. Utilizadores bloqueados e administradores não aparecem.

## 9. Tipos de utilizador

- **Jogador:** regista-se, inicia e termina sessão, altera os dados e a palavra-passe, cria o seu piloto, compra/vende/usa itens, aceita missões, corre contra rivais, consulta o ranking e o seu histórico.
- **Administrador:** não joga. Consulta utilizadores, bloqueia/desbloqueia utilizadores, cria/edita/remove itens, cria/edita missões, cria/edita rivais, consulta corridas, estatísticas e logs.
- Um utilizador bloqueado não consegue iniciar sessão.
- Palavras-passe guardadas com hash. As funções de administração só funcionam para o tipo Administrador.

## Teste de coerência das regras

Simulação à mão com a classe **Equilibrado** de nível 1 (100 integridade, 14 velocidade, 6 aderência, sem peças). Usamos o dano médio (multiplicador 1,0) e o jogador ataca primeiro.

**Contra o mais fraco: Tiago Novato** (40 integridade, 8 velocidade, 3 aderência)
- Dano do jogador: 14 − 3 = **11** por ronda → 40 / 11 ≈ **4 rondas** para vencer.
- Dano do rival: 8 − 6 = **2** por ronda → em 3 rondas recebe só 6 de dano.
- Resultado: o jogador vence com ~94 de integridade. Vence quase sempre, a sorte quase não interfere.

**Contra o mais forte: Rei da Noite** (200 integridade, 30 velocidade, 14 aderência)
- Dano do jogador: 14 − 14 = 0 → mínimo **1** por ronda → precisa de ~200 rondas.
- Dano do rival: 30 − 6 = **24** por ronda → 100 / 24 ≈ **5 rondas** para o jogador perder.
- Resultado: o jogador perde sempre. Não há sorte que compense (com 1,2 e nitro o dano do jogador sobe para 1 ou 2).

**Caso intermédio: Rui Turbo** (110 integridade, 17 velocidade, 8 aderência)
- Dano do jogador: 14 − 8 = 6 → 110 / 6 ≈ 19 rondas. Dano do rival: 17 − 6 = 11 → 100 / 11 ≈ 10 rondas. O jogador perde a menos que tenha melhorado o carro. Isto obriga a subir de nível e comprar peças.

**Conclusão:** o resultado depende principalmente dos atributos (velocidade, aderência e peças). A sorte (0,8 a 1,2 e nitro) só ajusta o dano em poucos pontos.
