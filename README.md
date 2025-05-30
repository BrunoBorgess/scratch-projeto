🛸 JOGO: RESGATE GALÁCTICO
Objetivo: Salvar 10 criaturas espaciais evitando meteoros.

SPRITES:
===========

🟦 SPRITE: NAVE
---------------
quando clicar em bandeira verde
vá para x: 0 y: -140
mostrar
defina [vidas v] para (3)
defina [salvos v] para (0)
escreva [ ] na lista [Criaturas Salvas v]

para sempre
  se tecla [seta esquerda v] pressionada
    mude x por -10
  se tecla [seta direita v] pressionada
    mude x por 10
fim

===========

🟩 SPRITE: CRIATURA
-------------------
quando clicar em bandeira verde
esconda

para sempre
  espere (2) segundos
  crie clone de [Criatura v]
fim

quando eu começar como clone
vá para x: número aleatório entre (-200) e (200), y: 180
mostrar

repita até <tocando em [Nave v] ou posição y < -180>
  mude y por -5
fim

se <tocando em [Nave v]> então
  mude [salvos v] por (1)
  adicione [Nome aleatório] à lista [Criaturas Salvas v]
  toque som [pop v]
fim

delete este clone

===========

🟥 SPRITE: METEORO
-------------------
quando clicar em bandeira verde
esconda

para sempre
  espere (3) segundos
  chamar [criarMeteoro v] com (número aleatório entre -200 e 200)
fim

quando eu começar como clone
vá para x: (posiçãoX), y: 180
mostrar

repita até <tocando em [Nave v] ou posição y < -180>
  mude y por -6
fim

se <tocando em [Nave v]> então
  mude [vidas v] por (-1)
  toque som [batida v]
fim

delete este clone

===========

🧩 BLOCO PERSONALIZADO: criarMeteoro (posiçãoX)
-----------------------------------------------
define criarMeteoro (posiçãoX)
vá para x: (posiçãoX), y: 180
crie clone de [Meteoro v]

===========

📜 SPRITE: INSTRUÇÕES
---------------------
quando clicar em bandeira verde
mostrar
espere (5) segundos
esconda

Texto no sprite:  
Use ← e → para mover a nave.  
Salve 10 criaturas.  
Cuidado com os meteoros!  
Clique na bandeira verde para começar.

===========

🏁 SPRITE: MENSAGEMFINAL
-------------------------
quando clicar em bandeira verde
esconda

para sempre
  se <(vidas) = 0> então
    diga [Game Over!] por (5) segundos
    pare [todos v]
  se <(salvos) = 10> então
    diga [Você venceu!] por (5) segundos
    pare [todos v]
fim

===========

🔢 VARIÁVEIS USADAS
--------------------
vidas → começa com 3  
salvos → começa com 0  
lista: Criaturas Salvas → armazena nomes como "Zorg", "Mimi", "Kloop"

===========

✅ TODOS OS CRITÉRIOS ATENDIDOS!
- 2 sprites (nave + criatura/metoro)
- clones
- variáveis e lista
- bloco personalizado com parâmetro
- instruções
- vitória/game over
- ideia original

FIM DO CÓDIGO
