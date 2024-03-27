# Adicione mais funcionalidades à sua aplicação

## Introdução

Nesta seção você irá criar uma página para mostrar os detalhes do parceiro de negócios selecionado para sua aplicação.

## Pré-requisitos:

- Você deve ter completado os exercícios anteriores
- Sua aplicação SAP Build deve estar funcionando e a página de lista deve carregar

## Passo 1: Criando uma nova página

Você adicionará uma nova página à sua aplicação e adicionará parâmetros de página para que você possa acessar dados de sua aplicação.

1. Na seção superior esquerda, clique no nome da sua página atual **Home**, que está destacado em azul claro para abrir o menu de páginas do SAP Build Apps.

2. Clique no botão **ADD NEW PAGE**.

    <p align="center"><img src="./images/ex2_part1_1.png" width="100%" /></p>

3. No campo **Page name**, preencha o nome da nova como `Details`, e então clique no botão **OK**. Sua nova página será criada e aberta.

4. Na página de detalhes, selecione o toggle button no canto superior direito para mudar a visualização de **VIEW** para **VARIABLES**.

5. Selecione a opção **PAGE PARAMETERS** no lado esquerdo da tela.

6. Clique no botão **ADD PARAMETER**.

    <p align="center"><img src="./images/ex2_part1_2.png" width="100%" /></p>

7. Criar um novo parâmetro, escolha o parâmetro criado para editar.

8. No lado direito da tela, altere o **Parameter name** para `partnerId`.

9. Por último clique em **SAVE**.

## Passo 2: Habilitar a navegação da Home Page para a Detail Page

Para exibir os detalhes do parceiro de negócios na página de detalhes, você precisa conectar a página **Home** e a página **Details**. Nesta seção, você primeiro criará uma nova lógica de navegação para passar o parâmetro da página criado na etapa anterior. Na página de detalhes, você carregará o endereço do parceiro de negócios passando o id do parceiro de negócios para a entidade **Business_Partners**.

1. No canto superior esquerdo, clique no nome da sua página atual **Details**, que está destacado em azul claro para abrir o menu de páginas do SAP Build Apps.

2. Selecione a página **Home** para criar uma lógica para passar os parâmetros de id e nome do parceiro de negócios da página **Home** para a página **Details**.

3. Selecione a primeira linha da lista.

4. At the bottom of App Builder where you can see **Add logic to LIST ITEM1**. Choose the arrow to open the logic canvas.
4. Na parte inferior do App Builder, onde você pode ver **Add logic to LIST ITEM1**. Escolha a seta para abrir o canvas de lógica.

    <p align="center"><img src="./images/ex2_part2_1.png" width="100%" /></p>

5. No menu de componentes no lado esquerdo, escolha **NAVIGATION → Open page** para adicionar uma função que navega para uma nova página.

6. Arraste e solte para a tela de lógica.

7. Passe o mouse sobre o **Component tap** e clique sobre o ponto redondo. Conecte os pontos dos componentes **Component tap** e **Open page**. Isso cria uma nova conexão e define a lógica para abrir uma nova página no evento de toque em um item na lista.

    <p align="center"><img src="./images/ex2_part2_2.png" width="100%" /></p>

8. Selecione o componente **Open page**.

9. No lado direito da tela, selecione **PROPERTIES → Parameters → partnerId**.

10. Selecione o botão **X**. Irá abrir um popup.

    <p align="center"><img src="./images/ex2_part2_3.png" width="100%" /></p>

11. Selecione **Data item in repeat**.

12. Selecione **current**.

13. Role a lista e selecione **id**, e então clique em **SAVE**.

    <p align="center"><img src="./images/ex2_part2_4.png" width="100%" /></p>

15. Clique no botão **SAVE** para salvar as alterações.

With this step now, you can pass the selected business partner id and name fields from the list to the details page.

Neste passo, você pode passar o id do parceiro de negócios selecionado a para a página de detalhes.

## Passo 3: Carregar os dados de um parceiro de negócios na página de detalhes

A página de detalhes recebe o ID do parceiro de negócios da página principal. Neste passo, o ID é usado para obter todos os dados de um parceiro de negócios selecionado.

1. Na parte esquerda superior da tela, clique  **Home** para navegar para a tela de seleção de páginas.

2. Selecione a página **Details** para mudar para a página de detalhes.

3. Selecione a aba **VARIABLES**.

4. Selecione a opção **DATA VARIABLES** no lado esquerdo da tela.

5. Clique na opção **ADD DATA VARIABLE**.

6. Selecione **Business_Partners** da lista.

7. Defina o **Data variable name** para `Business_Partners`.

8. Selecione o botão **Filter Conditions** no lado direito.

    <p align="center"><img src="./images/ex2_part3_1.png" width="100%" /></p>

9. Um popup será aberto. Selecione **Object with properties**.

    <p align="center"><img src="./images/ex2_part3_2.png" width="60%" /></p>

9. Selecione a opção **Add Condition**. No dropdown **Property**, selecione **id** e sob a propriedade **Compared Value**, clique no botão **ABC**.

    <p align="center"><img src="./images/ex2_part3_3.png" width="100%" /></p>

11. Selecione **Data and Variables**.

    <p align="center"><img src="./images/ex2_part3_4.png" width="100%" /></p>

12. Selecione **Page parameter**.

    <p align="center"><img src="./images/ex2_part3_5.png" width="100%" /></p>

13. Selecione **partnerId** em clique no botão salvar **SAVE**.

    <p align="center"><img src="./images/ex2_part3_6.png" width="100%" /></p>

14. Clique no botão **SAVE** para salvar as alterações na página.

15. Mude para o modo **VIEW**.

Agora, sua aplicação carrega os dados de um parceiro de negócios selecionado e armazena na variável de dados.

## Passo 4: Exibir o ID do parceiro de negócios na página de detalhes

Você irá alterar o cabeçalho da página de detalhes, para que ele exiba o parceiro de negócios atual.

1. Selecione a descrição padrão na página e delete pressionando **X**.

    <p align="center"><img src="./images/ex2_part4_1.png" width="100%" /></p>

2. Selecione o componente headline. No lado direito da tela, clique no botão **ABC** na seção **Content**.

    <p align="center"><img src="./images/ex2_part4_2.png" width="100%" /></p>

3. Selecione **Data and Variables**.

    <p align="center"><img src="./images/ex2_part4_3.png" width="80%" /></p>

4. Selecione **Page parameter**.

    <p align="center"><img src="./images/ex2_part4_4.png" width="80%" /></p>

5. Selecione **partnerId** e escreva `Partner ID` no campo **Set preview value**.

6. Clique no botão **SAVE**.

    <p align="center"><img src="./images/ex2_part4_5.png" width="100%" /></p>

## Passo 5: Exibir as informações do parceiro de negócios na página de detalhes

1. Arraste um componente **Layout->Row** da aba **CORE** no lado esquerdo para o canvas.

2. No lado direito em **PROPERTIES**, clique no botão **Repeat with**.

    <p align="center"><img src="./images/ex2_part5_1.png" width="100%" /></p>

3. No popup, selecione **Data and Variables → Data variable**.

4. Selecione **Business_Partners** na lista.

5. Choose **SAVE**.

    <p align="center"><img src="./images/ex2_part5_2.png" width="100%" /></p>

6. Arraste um componente **Text** da aba **CORE** para o lado esquerdo do componente **Row**.

7. No lado direito da tela, no campo **Content** preencha o campo com Nome do Parceiro.

    <p align="center"><img src="./images/ex2_part5_3.png" width="100%" /></p>

8. Arraste um componente **Text** da aba **CORE** para o lado direito do componente **Row**.

9. No lado direito da tela, clique no botão **ABC** na seção **Content**.

    <p align="center"><img src="./images/ex2_part5_4.png" width="100%" /></p>

10. Selecione **Data item in repeat**.

11. No campo select repeat selecione  **current**, no campo select repeat data property selecione **partnerName** e por último no campo Set preview value escreva Parceiro.

    <p align="center"><img src="./images/ex2_part5_5.png" width="100%" /></p>

12. Clique em **SAVE**.

13. Repita os passos anteriores para os seguintes campos:

    |Field name | Field type |
    |----|----|
    |Email | Text |
    |Address | Text |
    |Phone | Text |

    <p align="center"><img src="./images/ex2_part5_6.png" width="100%" /></p>

14. Clique no botão **SAVE** para salvar as alterações na página.


## Passo 6: Pré visualização da aplicação

1. Clique na aba **LAUNCH**.

2. Selecione a opção **OPEN PREVIEW PORTAL** e depois clique no botão **Open web preview**.

3. Selecione sua aplicação.

    <p align="center"><img src="./images/ex2_part6_1.png" width="70%" /></p>

A home page deve ser parecida com a imagem abaixo:

<p align="center"><img src="./images/ex2_part6_3.png" width="100%" /></p>

A página de detalhes deve ser parecida com a imagem abaixo:

<p align="center"><img src="./images/ex2_part6_4.png" width="100%" /></p>


## Passo 7: Adicionando opção de chamada

1. Ná página de detalhes, arraste um componente **Button** da aba **CORE** para o canvas, preencha o campo label com o valor `Ligar para o Parceiro de Negócios` e por último selecione o campo abaixo para adicionar uma lógica ao botão.

    <p align="center"><img src="./images/ex2_part7_1.png" width="100%" /></p>

2. Clique em **MARKETPLACE**.

    <p align="center"><img src="./images/ex2_part7_2.png" width="70%" /></p>

3. Procure por **Open URL** e clique no resultado destacado abaixo.

    <p align="center"><img src="./images/ex2_part7_3.png" width="100%" /></p>

4. Clique no botão **Install**.

5. Arraste o **Open URL** para o canvas.

6. Conecte os dois **Componentes** passando o mouse sobre os pontos finais e conectando-os.

    <p align="center"><img src="./images/ex2_part7_4.png" width="100%" /></p>

7. Clique no botão **Open URL** e pressione o botão **ABC**.

    <p align="center"><img src="./images/ex2_part7_5.png" width="100%" /></p>

8. Clique em **Formula**.

9. E escreva a seguinte expressão `""tel:"+data.Business_Partners[0].phone`.

    <p align="center"><img src="./images/ex2_part7_6.png" width="100%" /></p>

10. Clique em **Save**.

11. Parabéns, você adicionou a função de **Ligar** para o seu aplicativo e pode testar no **Web Preview**.

## Parabéns

Incrível! Você completou o Exercício 2. 🥳

Você pode voltar para a página Overview [Overview](../../#exercises).  
Ou você pode seguir para o próximo exercício [Exercise 3](../ex3/), navegue para lá clicando no link [this link](../ex3/).

