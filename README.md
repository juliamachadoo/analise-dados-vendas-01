# Análise de dados de Vendas 


## Sobre o Conjunto de Dados
- O dataset utilizado neste projeto contém informações detalhadas sobre transações de vendas realizadas em uma loja. Ele inclui registros de produtos vendidos, clientes, métodos de pagamento, descontos aplicados, taxas de envio e avaliações dos clientes.
- Este conjunto de dados será utilizado para realizar uma análise exploratória e obter insights sobre o comportamento das vendas e dos clientes.
- O conjunto analisado, após análise dos dados, começaram a ser gravados (a partir da primeira data da coluna 'TransactionDate') no dia 03/08/2024 e o último registro foi em 30/01/2025. Ou seja, temos os dados de 6 meses de transações.

## Estrutura do Dataset<br>
- O dataset contém X linhas e 32 colunas, sendo elas:<br>
    - <b>📦 Informações sobre os Produtos:</b><br>
    - <b>ProductID</b> – Identificador único do produto.
    - <b>ProductName</b> – Nome do produto vendido.<br>
    - <b>ProductCategory</b> – Categoria do produto (ex: Eletrônicos, Roupas).<br><br>
    
    - <b>📊 Informações sobre as Vendas:</b><br>
    - <b>TransactionID</b> – Identificador único da transação.<br>
    - <b>TransactionDate</b> – Data em que a venda foi realizada.<br>
    - <b>TimeOfDay</b> – Período do dia em que a transação ocorreu (manhã, tarde, noite).<br>
    - <b>SalesQuantity</b> – Quantidade de unidades vendidas na transação.<br>
    - <b>SalesPrice</b> – Preço original do produto antes de descontos.<br>
    - <b>FinalSalePrice</b> – Valor final pago pelo cliente após descontos.<br>
    - <b>SalesChannel</b> – Canal de vendas utilizado (Online, Loja Física).<br>
    - <b>PromoCodeUsed</b> – Indica se um código promocional foi aplicado na compra (Sim/Não).<br>
    - <b>DiscountAmount</b> – Valor do desconto aplicado à transação.<br>
    - <b>DiscountPercentage</b> – Percentual de desconto aplicado.<br>
    - <b>SalesTax</b> – Imposto sobre a venda.<br><br>
    
    - <b>💳 Informações sobre Pagamento<br>
    - <b>PaymentMethod</b> – Forma de pagamento utilizada (Cartão, Dinheiro, Pix, Boleto).<br>
    - <b>PaymentStatus</b> – Status do pagamento (Pago, Pendente, Cancelado).<br>
    - <b>TransactionStatus</b> – Status geral da transação (Concluída, Pendente, Cancelada).<br><br>
    
    - <b>🛍️ Informações sobre o Cliente<br>
    - <b>CustomerID</b> – Identificador único do cliente.<br>
    - <b>CustomerAge</b> – Idade do cliente.<br>
    - <b>CustomerGender</b> – Gênero do cliente (Masculino, Feminino, Outros).<br>
    - <b>CustomerLocation</b> – Localização geográfica do cliente.<br>
    - <b>LoyaltyProgramMember</b> – Indica se o cliente faz parte do programa de fidelidade (Sim/Não).<br>
    - <b>CustomerFeedbackRating</b> – Avaliação do cliente sobre a compra (nota de 1 a 5).<br><br>
    
    - <b>🔄 Informações sobre Devoluções<br>
    - <b>ReturnFlag</b> – Indica se a compra foi devolvida (Sim/Não).<br>
    - <b>ReturnReason</b> – Motivo da devolução (Produto com defeito, Não gostou, Outro).<br><br>
    
    - <b>🚚 Informações sobre Envio<br>
    - <b>StoreLocation</b> – Localização da loja onde a compra foi realizada.<br>
    - <b>Region</b> – Região geográfica da venda.<br>
    - <b>ShippingMethod</b> – Método de envio utilizado (Correios, Transportadora, Retirada na Loja).<br>
    - <b>ShippingFee</b> – Valor pago pelo envio.<br>
    - <b>ShippingStatus</b> – Status da entrega (Entregue, Em Trânsito, Atrasado).<br><br>
    
    - <b>📈 Informações sobre Cross-Selling e Upselling<br>
    - <b>CrossSellProducts</b> – Produtos recomendados junto com a compra.<br>
    - <b>UpsellProducts</b> – Produtos de maior valor sugeridos na venda.<br>

## KPI's para análise
  - Ticket Médio das Vendas
  - Total de vendas por período (dia, mês, ano)
  - Comparação de vendas por categoria e produto
  - Horário com maior frequencia de compra (Manhã, tarde ou noite)
  - Motivo de retorno dos produtos
  - Taxa de devolução
  - Compras por região (Norte, sul, leste, oeste)
  - Comparar canais de compra (Online, Loja física)
  - Tipos de Pagamento
  - Perfil do Cliente (Idade,gênero, clube de fidelidade)

## Observações e Insights sobre o Dataset
  - Observa-se que na nas colunas ReturnReason, CrossSellProducts e UpsellProducts existem valores NaN.  Os valores com NaN dessas 3 colunas podem ser modificados por 'No', pois são valores admitem essa mudança, uma vez que ReturnReason é a razão de devolução e o valor 'No' significaria que não houve devolução. #Já as colunas CrossSellProducts e UpsellProducts avaliam se houveram ou não compras conjuntas ou upgrade de equipamento. Logo, as que são NaN serão substituidas por 'No' para melhor análise.
  - Após análise percebemos que não podemos fazer muitas comparações entre o ano de 2024 e 2025 pois foram gravados 5 meses de dados do ano de 2024 e apenas 1 mês do ano de 2025, não sendo possivel fazer a comparação de vendas por ano, mês e dia.
  - O valor total das vendas por categoria foi bem equilibrado, não tendo uma categoria que se mostrou mais rentável que outra. Bem como a quantidade de produtos por categoria. Ou seja, a quantidade de produtos por categoria ficou bem equilibrada, não tendo uma categoria que se destacasse nas vendas;
  - O produto mais vendido, vendeu 125 unidades com o valor unitário de $51,00 (Categoria: Clothing) . Já o produto menos vendido, vendeu somente 2 unidades, custando $232,00 cada unidade (Categoria: Furniture). Porém, temos produtos que chegam a até $500,00 (Categoria: Eletronics);
  - A quantidade de compras não teve muita variação no horário do dia (Manhã, tarde ou noite), ou seja, não existe um horário do dia que se compra mais que o outro;
  - As compras feitas por região também não possuiam muita variação, mantendo-=se as vendas equilibradas em todas as regiões;
  - Sobre o perfil do cliente, não houve muita dissiparidade em relação ao gênero. Porém, observou-se que os clientes que mais compram nas lojas possuem idades entre 31 - 60 anos. E podemos chegar as seguintes conclusões:
      🎯 1. Maior poder de compra<br>
        📌 Indivíduos nessa faixa etária geralmente têm estabilidade financeira, permitindo compras mais frequentes e de maior valor.<br>
        ✅ Oportunidade: Criar estratégias para aumentar o ticket médio, como combos, planos de assinatura e programas de fidelidade.

    🛒 2. Preferência por praticidade<br>
        📌 Esse grupo pode buscar compras rápidas e eficientes, sem perder muito tempo em pesquisas.<br>
        ✅ Oportunidade: Oferecer recomendações personalizadas, criar um atendimento ágil e facilitar a experiência de compra.
    
    📦 3. Maior lealdade à marca<br>
        📌 Clientes entre 31-60 anos tendem a ser mais fiéis a marcas que oferecem qualidade e confiança.<br>
        ✅ Oportunidade: Investir em pós-venda, experiências exclusivas para clientes recorrentes e melhoria do atendimento para fortalecer a relação.
    
    📊 4. Diferentes hábitos de compra dentro da faixa etária<br>
        📌 Dentro do intervalo 31-60 anos, pode haver subgrupos com comportamentos distintos:<br>
          - 31-40 anos: Mais conectados ao digital, podem pesquisar antes de comprar.<br>
          - 41-50 anos: Valorizam mais a experiência de compra, seja online ou presencial.<br>
          - 51-60 anos: Podem priorizar segurança, confiança na marca e recomendações de terceiros.<br>
      ✅ Oportunidade: Segmentar campanhas de marketing e criar estratégias diferentes para cada subgrupo.

## Pontos de atenção
  - O maior ponto de atenção da loja se deve as devoluções, percebemos que mais de 700 produtos foram devolvidos, enquanto apenas pouco mais de 250 não foram, ou seja, a empresa deve procurar investigar mais afundo para saber o porque dos cliente estão devolvendo tantos produtos. É sabido, através de análise, que dos quase 750 produtos devolvidos, quase 250 eram defeituosos e mais de 250 foram por mudança de pensamento dos clientes:
    - 1️⃣ Redução de produtos defeituosos (247 devoluções)<br>
      🔹 Melhoria no controle de qualidade → Implementar inspeções mais rigorosas antes do envio.<br>
      🔹 Parceria com fornecedores confiáveis → Garantir que os produtos sejam fabricados com qualidade superior.<br>
      🔹 Embalagens mais seguras → Para evitar danos durante o transporte.<br><br>
    - 2️⃣ Redução de devoluções por mudança de ideia (258 devoluções)<br>
      🔹 Descrições detalhadas e fotos realistas → Melhorar a apresentação dos produtos na loja online para alinhar expectativas.<br>
      🔹 Vídeos demonstrativos e avaliações de clientes → Ajudam a reforçar a decisão de compra.<br>
      🔹 Política de troca flexível → Em vez de devolução, oferecer crédito para outra compra.<br><br>
    - 3️⃣ Análise mais profunda dos outros motivos (241 devoluções)<br>
      🔹 Coletar feedback detalhado dos clientes → Usar pesquisas e análises para entender melhor os motivos exatos das devoluções.<br>
      🔹 Atendimento ao cliente proativo → Suporte rápido pode evitar cancelamentos antes da devolução.<br>
    - Outro ponto de atenção é sobre o canal de vendas, foi observado que as vendas online (Site e mobile app) somam mais de 65% das vendas, ou seja,se for o foco da empresa ampliar suas vendas em lojas físicas, é possível criar estratégias direcionadas para tornar a experiência nas lojas físicas mais atraente e competitiva em relação ao online.

## Link Dataset
- [Dataset](https://www.kaggle.com/datasets/harinkl/sales-data)
