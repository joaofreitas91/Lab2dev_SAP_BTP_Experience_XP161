# Criando sua primeira aplicação com SAP Build Apps

## Introdução

Nesta seção, você irá criar uma nova aplicação usando o SAP Build Apps.

## Pré-requisitos

- Ter completado o exercício anterior e as etapas de configuração.

## Passo 1: Iniciar o SAP Build Apps

1. Abra sua **SAP BTP subaccount**.

2. No menu lateral da sua subaccount, navegue para **Services → Instances and Subscriptions**.

3. Na aba **Subscriptions**, procure **SAP Build Apps** e escolha **Go to Application** para abrir a página de  desenvolvimento de aplicativos.

    <p align="center"><img src="./images/ex1_step1_3.png" width="100%" /></p>

4. Entre na aplicação usando suas credenciais de provedor de identidade.    

## Passo 2: Criando uma aplicação usando SAP Build Apps

**Criando um projeto**

1. No Lobby do SAP Build ,selecione a opção **Create** e escolha **Build an Application**.

    <p align="center"><img src="./images/ex1_step2_1.png" width="80%" /></p>

2. Escolha a opção **SAP Build Apps**

    <p align="center"><img src="./images/ex1_step2_1_2.png" width="80%" /></p>

3. Escolha **Web & Mobile Application**.

    <p align="center"><img src="./images/ex1_step2_2.png" width="80%" /></p>

4. Defina um nome para o projeto no seguinte formato ``BTP_EXP_##`` onde **##** é um identificador único como um número de inscrição ou o seu nome, por exemplo, `BTP_EXP_01`.

5. Você pode adicionar uma descrição curta no campo **Short Description** mas esse campo não é obrigatório.

6. Selecione a opção **Create**.

    <p align="center"><img src="./images/ex1_step2_5.png" width="60%" /></p>


7. O Projeto criado será aberto no **App Builder** que é a página central para construir sua aplicação incluindo a interface do usuário, lógica e integração de dados.

8. Selecione **Headline**.

9. Procure a aba **Properties** no menu à direita para alterar o conteúdo do título. Escolha **Content** e altere o conteúdo de **Headline** para **Meus Parceiros de Negócios**.

    <p align="center"><img src="./images/ex1_step2_8.png" width="100%" /></p>

10. Procure o campo de texto no UI canvas no centro da tela e escolha **x** para remover este componente.

    <p align="center"><img src="./images/ex1_step2_9.png" width="50%" /></p>

11. Clique na página em branco. No lado direito, em **Properties**, escolha **Page name**.

12. Altere o nome da página para **Home**.

    <p align="center"><img src="./images/ex1_step2_11.png" width="100%" /></p>

## Passo 3: Habilitando autenticação

Para consumir dados de um sistema SAP backend ou mock data que são configurados como uma destination SAP BTP, você precisa habilitar a autenticação.

1. Clique na aba **AUTH** no topo do App Builder.

2. Clique em habilitar autenticação.

    <p align="center"><img src="./images/ex1_step3_a.png" width="100%" /></p>

3. Selecione **SAP BTP Authentication** e clique em **OK**. Isso habilita a autenticação para o projeto.

## Passo 4: Adicionando uma fonte de dados local

Para adicionar uma fonte de dados local você precisa seguir os seguintes passos:

1. Clique na aba **Data** no topo do App Builder.

2. Procure a seção **No system integrated** e clique na opção  **ADD INTEGRATION**.

    <p align="center"><img src="./images/ex1_step3_1.png" width="100%" /></p>

3. Na próxima tela, selecione **BTP Destinations**.

4. Pesquise e selecione a destination `btp_experience_build_backend_dest`.

5. Clique em instalar integração.

6. Dentro da entidade de dados, selecione **Business_Partner**.

    <p align="center"><img src="./images/ex1_step3_2.png" width="100%" /></p>

7. Na próxima tela, clique no botão **Enable Data Entity**.

    <p align="center"><img src="./images/ex1_step3_3.png" width="100%" /></p>

8. Escolha **Save** no topo do app builder. Isso adiciona a fonte de dados ao seu projeto. Escolha **UI Canvas** para voltar para a visualização do designer de UI.

9. Agora você adicionou uma fonte de dados para sua aplicação SAP Build Apps.

## Passo 5: Criando uma página de lista de parceiros de negócios

Para criar uma página exibindo a lista de parceiros de negócios, você precisa primeiro criar **data variable**.

**Data Variable**

Um data variable é essencialmente a mesma coisa que uma page variable que existe no contexto da página atual e não é acessível de outras páginas, e desaparece se a página for removida de navegação. A diferença é que ela obtém seu esquema do recurso de dados ao qual aponta e vem com a lógica padrão incluída.

### **Criando um Data Variable**

Vamos criar um data variable para armazenar os resultados dos dados do parceiro de negócios provenientes da fonte de dados.

1. Na aba UI CANVAS, escolha o botão de alternância para mudar de **VIEW** para **VARIABLES**.

2. No lado esquerdo do app builder, escolha **DATA VARIABLES**.

3. Agora, escolha **ADD DATA VARIABLE** e selecione **Business_Partners**.

    <p align="center"><img src="./images/ex1_step4_3.png" width="100%" /></p>

4. Altere o campo **Data variable name** para `Business_Partners`

   <p align="center"><img src="./images/ex1_step4_4.png" width="100%" /></p>

5. Clique em **SAVE**.

Agora que a data variable foi criada, alterne de volta para o modo **VIEW**.

### **Criando uma página de lista de parceiros de negócios**

Neste passo você irá criar uma página de lista de parceiros de negócios no app builder.

**Verifique se os dados estão visíveis na interface do usuário**

1. No painel esquerdo do UI CANVAS, você verá a guia **CORE**, role para a seção **LISTS** e escolha **List item**.

    <p align="center"><img src="./images/ex1_step4_n1.png" width="30%" /></p>

2. Arraste o **List item** para a página da aplicação.

3. No lado direito, na seção **PROPERTIES**, role para **Repeat with** e clique no botão para fazer o bind.

    <p align="center"><img src="./images/ex1_step4_n3.png" width="100%" /></p>

4. Um popup será aberto. Selecione **Data and Variables**, então escolha **Data variable**.

    <p align="center"><img src="./images/ex1_step4_n4.png" width="80%" /></p>

5. Selecione **Business_Partners** na lista e clique em **SAVE**.

6. Você configurou que a lista é populada com a variável de dados que obtém os dados do parceiro de negócios.

### **Selecionando os campos de exibição para a lista**

Agora vamos definir quais campos gostaríamos de exibir na interface do usuário na lista de parceiros de negócios.

1. Selecione a lista.

2. Vá para **PROPERTIES**.

3. Clique no botão do campo Primary Label **ABC**.

    <p align="center"><img src="./images/ex1_step4_nn3.png" width="40%" /></p>

4. Selecione a opção **Data item in repeat**.

5. Selecione a opção **current**.

6. Selecione a opção **partnerName**

7. Digite `Partner Name` no campo **Set preview value** e clique em **SAVE**.

    <p align="center"><img src="./images/ex1_step4_nn6.png" width="50%" /></p>

8. Vá para **PROPERTIES**.

9. Clique no botão do campo Secondary Label **ABC**.

10. Selecione a opção **Data item in repeat**.

11. Selecione a opção **current**.

12. Selecione a opção **id**

13. Digite `Id` no campo **Set preview value** e clique em **SAVE**.

    <p align="center"><img src="./images/ex1_step4_nn7.png" width="50%" /></p>

## Passo 6: Pré-visualização da aplicação

1. Clique na aba **LAUNCH**.

2. Selecione a opção **OPEN PREVIEW PORTAL**.

    > Uma nova aba será aberta. Nessa tela você terá duas opções para pré visualização da sua aplicação. Você pode clicar no botão **Open web preview** para visualizar a aplicação no navegador baixar o aplicativo para Android ou iOS e gerar um PIN para visualizar a aplicação no seu dispositivo móvel.

3. Clique no botão **Open web preview**.

4. Selecione o aplicativo que você acabou de criar.

5. O aplicativo será exibido no portal de pré-visualização.

    <p align="center"><img src="./images/ex1_step5_2.png" width="100%" /></p>

Agora você pode visualizar a lista de parceiros de negócios que você acabou de criar.

## Parabéns!

Incrível! Você completou o Exercício 1. 🥳

Você pode voltar para a página Overview [Overview](../../#exercises).  
Ou você pode seguir para o próximo exercício [Exercise 2](../ex2/), navegue para lá clicando no link [this link](../ex2/).
