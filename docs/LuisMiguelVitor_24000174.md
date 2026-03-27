# Avaliação — Engenharia de Software
**Sistema Integrado de Gestão de Farmácia — MVP Definido pelo Estudante**

Aluno: *Luis Miguel Vitor*  
RA: *24000174*  
Data: *23/03/2026*  

---

# 1. Definição do MVP
Meu MVP cobre o processo de venda de medicamentos e produtos a indentificação ou cadrasto do cliente ate a finalização de venda, integrando automaticamente o controle de estoque e o resgitro financeiro, O sistema vai permitir que o atentede consulte produtos, verifique a disponibilidade no estoque, regitrar intens da venda, esolher a froma de pagamento e emitir um comprovante ao final da compra, no MVP tambem tera a atualizção automatica do estoque apos cada venda e no caso de venda a prazo, a geração de um laçamento em contas a receber com controle de vencimento e staus.

Ficou de fora do meu MVP as funcionalidade de compras de fornecedores, gestões completa de contas a pagar, relátorios, transferências entre unidades e adiministração geral do sistema.

As escolhas foram feitas porque o preocesso de venda é o principal fluxo operacional da farmacia e integra diferente áreas, sendo suficeinte para demonstrar o funcionamento essencial do sistema.
---

# 2. Regras de Negócio
Liste e descreva **cada RN** de forma clara.

**RN01 Venda somente com o estoque dispónivel -**
O sistema não deve realizar a venda do produto caso não tenha q quantidade suficiente no istema.

**RN02 Atualizção automática do estoque —** 
Após realizar uma venda o estoque do produto que foi vendido , deve ser retirado a quantidade que foi vendida.

**RN03 Cadastro obrigatório para vendas a prazo —**
Todas as vendas relaizadas a a prazo so devem serem feitas para clientes devidamente cadastrados no sistema.

**RN04 Geração automática de contas a receber —**
Toda vendo a prazo deve gerar uma lançamento em contas a receber, contendo informações como valor, data de vencimento.

**RN05 Emissão obrigatória de coimprovante —**
Emissão obrigatória de coimprovante Ao final de cada venda, o sistema deve emitir um comprovante contendo os dados da operção e intens vendios e a forma do pagemento.

---

# 3. Requisitos Funcionais
Liste os requisitos funcionais do seu MVP.

**RF01 Consultar produtos —** 
O sistema de permiter que o atentede pequeise o prodsuto por nome e codigo de barras.

**RF02 Verificar disponibilidade em estoque —** 
O sistema deve informar a quantidade disponivel do produto disponivel antes da venda.

**RF03 Registrar itens da venda —** 
O sistema deve permiter a inclusisao de uma ou mais intns na venda, contendo sua quantidade.

**RF04 Identificar ou cadastrar cliente —** 
O sistema deve permitir localizar um cliente já cadastrado ou realizar um cadasto caso não exista.

**RF05 Selecionar forma de pagamento —**
O sistema deve permitir escolher entre pagmento a vista ou a prazo.

**RF06 Finalizar venda —** 
O sistema deve registrar automaticamente a quantidade dos produtos vendidos no estoque.

**RF07 Atualizar estoque automaticamente —** 
O sistema deve reduzir automaticamente a quando do prosuto quando ele forvendido.

**RF08 Gerar conta a receber para vendas a prazo —**
O sistema deve criar Automaticamente um registro em contas a receber quando venda for realizada a prazo.

---

# 🛡 4. Requisitos Não Funcionais
Liste os RNFs do sistema conforme seu MVP.

**RNF01 Segurança de acesso —**
O sistema deve permitir acessoa somente a pessoas autorizadas autenmticando por meio de login e senha

**RNF02 Tempo de resposta —**
O sistema deve responder as opreçoes de consulta venda e tempo adequado, não ultrapassando alguns segundo.

**RNF03 Disponibilidade —**
O sistema deve estar disponiovel durante o horário de funcionamento da farmácia, evitando interrupções no atendimento

**RNF04 Usabilidade —**
O sistema deve estar disponiovel durante o horário de funcionamento da farmácia, evitando interrupço~es no atendiment

---

# 5. Casos de Uso
### Inserir **diagrama de casos de uso geral**, demonstrando claramente:
1<img width="449" height="728" alt="image" src="https://github.com/user-attachments/assets/a2f50932-9db9-48c5-bc07-fcdecb0aef8b" />
2<img width="448" height="229" alt="image" src="https://github.com/user-attachments/assets/8b9b1781-939f-4e69-90df-185b8e0de12f" />



---

# 6. Documentação dos Casos de Uso
Para **cada caso de uso**, utilize o template abaixo:
---

## **UC01 — Realizar venda**
**Ator(es):*Atendente*  
**Descrição:*Permiete o atendente fazer venda ao cliente, verificar estoque, forma de pagamento e finalizar operçaõ*  
**Pré-condições:*O atentde deve esta autenticado no sistema e os produtos cadratado*  
**Pós-condições:*Venda registrada no sistema e estoque atualizado*  

### Fluxo Principal
1.  O atendente incia a venda e informa o produto desejado.
2.  O sistema verifica a disponibilidade no estoque.
3.  O atendente seleciona a froma de pagamento
4.  O sistema finaliza a venda e atualiza o estoque

### Fluxos Alternativos / Exceções
- FA01 —  Produto sem estoque - se não houver quantidade no estoquem o sistema inofrma indiponibilidade e não realiza a venda
- FA02 —  Cliente não casdastrado - atendente pode realizar o cadatro do cliente antes de continuar.

### Relacionamentos
- **Include:**
  Consultar produto
  Verificar estoque
  regitrar intes da venda
  selecionar forma de oagemnto
  finalizar venda
- **Extend:**
  Cadastrar cliente

## **UC02 — Consultar Produto**
**Ator(es):*Atendente*  
**Descrição:*Permiete pesquisar um produto pelo nome ou código de barras*  
**Pré-condições:*Produto cadrastado no sistema*  
**Pós-condições:*informções do produro são exibidas*  

### Fluxo Principal
1.  O atendente informa o nome ou código do produto.
2.  O sistema localiza o produto.
3.  O sistema exibe os dados do produto.

### Fluxos Alternativos / Exceções
- FA01 — Produto não encontrado - O sistema informa que o produto não está cadastrado.
- FA02 — Código inválido - O sistema solicita que seja informado um dado válido.

### Relacionamentos
nenhum

## **UC03 — Verificar estoque**
**Ator(es):*Atendente*  
**Descrição:*Permiete consultar a quantidade disponível de um produto*  
**Pré-condições:*Produto existente no sistema.*  
**Pós-condições:*Quantidade disponível exibida.*  

### Fluxo Principal
1.  O atendente seleciona o produto.
2.  O sistema consulta o estoque de unidade.
3.  O sistema exibe a quantidade disponivel.

### Fluxos Alternativos / Exceções
- FA01 — Produto sem estoque - O sistema informa indisponibilidade.
- FA02 — Produto não localizado - O sistema informa erro na consulta.

### Relacionamentos
nenhum

## **UC04 — Registrar itens da venda**
**Ator(es):*Atendente*  
**Descrição:*Permite adicionar produtos e quantidades à venda.*  
**Pré-condições:*Venda iniciada.*  
**Pós-condições:*Itens incluídos na venda.*  

### Fluxo Principal
1.  O atendente seleciona o produto.
2.  Informa a quantidade.
3.  O sistema adiciona o item à venda.

### Fluxos Alternativos / Exceções
- FA01 — Quantidade inválida - O sistema solicita valor válido.
- FA02 — Estoque insuficiente - O sistema impede a inclusão do item.

### Relacionamentos
nenhum

## **UC05 — Identificar cliente**
**Ator(es):*Atendente*  
**Descrição:*Permite localizar cliente cadastrado*  
**Pré-condições:*Cliente cadastrado no sistema.*  
**Pós-condições:*Cliente identificado na venda*  

### Fluxo Principal
1.  O atendente informa os dados do cliente.
2.  O sistema busca o cadastro.
3.  O sistema exibe as informaçõesl.

### Fluxos Alternativos / Exceções
- FA01 — Cliente não encontrado - O sistema oferece cadastro.
- FA02 — Produto não localizado - O sistema solicita nova informação

### Relacionamentos
nenhum

## **UC06 — Cadastrar cliente**
**Ator(es):*Atendente*  
**Descrição:*Permite registrar novo cliente no sistema.*  
**Pré-condições:*Cliente não cadastrado.*  
**Pós-condições:*Cliente registrado no sistema.*  

### Fluxo Principal
1.  O atendente informa os dados.
2.  O sistema valida as informações.
3.  O cadastro é salvo

### Fluxos Alternativos / Exceções
- FA01 — Dados obrigatórios ausentes - O sistema solicita preenchimento completo.
- FA02 — Cliente já cadastrado - O sistema informa duplicidade.

### Relacionamentos
nenhum

## **UC07 — Selecionar forma de pagamento**
**Ator(es):*Atendente*  
**Descrição:*Permite escolher pagamento à vista ou a prazo.*  
**Pré-condições:*Venda em andamento.*  
**Pós-condições:*Forma de pagamento registrada.*  

### Fluxo Principal
1.  O sistema apresenta opções.
2.  O atendente escolhe a forma.
3.  A escolha é registrada.

### Fluxos Alternativos / Exceções
- FA01 —Forma inválida - O sistema solicita nova escolha.
- FA02 — Pagamento recusado - O sistema informa falha e permite outra opção.

### Relacionamentos
nenhum

## **UC08 — Finalizar venda**
**Ator(es):*Atendente*  
**Descrição:*Conclui a venda no sistema.*  
**Pré-condições:*Itens e pagamento definidos.*  
**Pós-condições:*Venda registrada no sistema.*  

### Fluxo Principal
1.  O atendente confirma a operação.
2.  O sistema registra a venda.
3.  O sistema confirma conclusão.

### Fluxos Alternativos / Exceções
- FA01 — Falha no registro - O sistema informa erro e não conclui.
- FA02 — Pagamento recusado - O processo é encerrado sem salvar.

## **UC09 — Gerar contas a receber**
**Ator(es):*Sistema*  
**Descrição:*Cria registro financeiro para vendas a prazo.*  
**Pré-condições:*Venda realizada a prazo.*  
**Pós-condições:*Conta registrada no sistema financeiro.*  

### Fluxo Principal
1.  O sistema identifica venda a prazo
2.  Gera o lançamento financeiro
3.  Define data de vencimento.

### Fluxos Alternativos / Exceções
- FA01 — Erro na geração- O sistema informa falha..
- FA02 — Pagamento recusado - O sistema solicita correção.

## **UC10 — Emitir comprovante**
**Ator(es):*Sistema*  
**Descrição:*Emite comprovante da venda.*  
**Pré-condições:*Venda finalizada.*  
**Pós-condições:*Comprovante emitido*  

### Fluxo Principal
1.  O sistema gera o comprovante
2.  Exibe ou imprime o documento

### Fluxos Alternativos / Exceções
- FA01 — Falha na impressão- O sistema informa erro.
- FA02 — Impressora indisponível - O sistema permite salvar digitalmente.



### Inserir o diagrama de atividades do Caso de Uso, demonstrando tudo o fluxo princial e alternativos/exceções.

---

> Repita essa estrutura para **todos os seus casos de uso** (mínimo 10).

1 <img width="620" height="942" alt="image" src="https://github.com/user-attachments/assets/feb6599d-dd1b-4e7c-833b-f2c2fed021dd" />

2 <img width="392" height="227" alt="image" src="https://github.com/user-attachments/assets/e14520a7-ec96-4ba3-bdba-1632750fdaf0" />

3 <img width="357" height="282" alt="image" src="https://github.com/user-attachments/assets/7b0797ba-00a7-40f1-98bb-2fc15779ea86" />

4 <img width="560" height="331" alt="image" src="https://github.com/user-attachments/assets/989deb4a-708e-4d59-991d-f7eb9582a78b" />

5 <img width="271" height="227" alt="image" src="https://github.com/user-attachments/assets/1605c20c-2d04-4471-8a8c-39b09f84cc90" />

6 <img width="472" height="276" alt="image" src="https://github.com/user-attachments/assets/f96ad351-33e0-4e8f-82ee-0f55461cac43" />

7 <img width="536" height="331" alt="image" src="https://github.com/user-attachments/assets/da91cae1-8bec-429d-8114-564872237253" />

8 <img width="260" height="227" alt="image" src="https://github.com/user-attachments/assets/c04f7561-2b61-4865-81b9-1975801fd496" />

9 <img width="374" height="282" alt="image" src="https://github.com/user-attachments/assets/f2348e88-f03e-4d16-b444-374451b066a8" />

10 <img width="374" height="282" alt="image" src="https://github.com/user-attachments/assets/d1a1e18c-332a-4d0b-b271-80e230e3d882" />




