# Alisson dos Santos Pereira

## Introdução
Sou formado como Técnico em Automação pela Escola Técnica Estadual (ETEC) e, desde 2023, atuo na área de desenvolvimento de software.

Minhas principais tecnologias são **Angular**, **.NET** e **PHP**, e tive a oportunidade de aplicar esses conhecimentos em empresas como a **DBsnoop**.  
Além disso, também possuo experiência em bancos de dados, metodologias ágeis e boas práticas de programação, o que complementa minha atuação como desenvolvedor full stack.
<div align="center">

<img src="https://github.com/user-attachments/assets/830846e7-6b8b-4ae7-9689-d0e3aba08a3c" alt="Imagem ilustrativa" width="400"/>

</div>

---

## Contatos
- **GitHub:** [alisson-C-angular-php](https://github.com/alisson-C-angular-php)
- **LinkedIn:** [Alisson Pereira](https://www.linkedin.com/in/alisson-pereira-16492224b/?originalSubdomain=br)

---

## Meus Principais Conhecimentos
- **.NET**
- **C#**
- **Angular**
- **TypeScript**
- **HTML/CSS**
- **SQL**

---

## Meus Projetos

### 2022 - Primeiro Semestre
- [Link para o README do Projeto 1º Semestre](https://github.com/tn-api1sem/api)

<details>
<summary><b> 2022-1 </b></summary>

# 🎯 Projeto: Portal de Avaliação 360° – FATEC

## 🏢 Empresa Parceira: FATEC

A **Faculdade de Tecnologia (FATEC)** foi a instituição parceira deste projeto, cuja proposta visava aprimorar o processo de avaliação comportamental e colaborativa entre membros de times de desenvolvimento ágil.

---

## 📌 Desafio

O desafio consistiu na criação de um **portal de avaliação 360 graus**, com foco no desenvolvimento e acompanhamento de **soft skills** entre os participantes de projetos ágeis. As regras estabelecidas incluíram:

* Cada usuário deve realizar uma **autoavaliação**.
* Os usuários também avaliam **todos os demais membros de sua equipe**.
* Avaliações são feitas com base em critérios predefinidos de **habilidades interpessoais (soft skills)**.
* Líderes de equipe são avaliados pelo líder do grupo, enquanto os **Product Owners (POs)** são avaliados pelo **Fake Client** (cliente fictício designado).

---

## 💡 Solução Desenvolvida

Foi implementado um **portal web completo** para gerenciar e centralizar o processo de avaliação contínua durante os ciclos de sprint.

### Principais Funcionalidades:

* Avaliação 360° entre membros da equipe.
* Painel interativo com **dashboard de desempenho** por sprint.
* Acompanhamento da **evolução dos resultados** ao longo do tempo.
* Funcionalidades administrativas para:

  * Cadastro e gestão de usuários.
  * Configuração e manutenção das equipes de trabalho.
  * Definição do cronograma de sprints e liberação dos ciclos de avaliação.

---

## ⚙️ Tecnologias Utilizadas

* **Backend:**

  * **Python** com **FastAPI** – Criação de endpoints RESTful, rotas protegidas, validação de dados com Pydantic e estruturação de regras de negócio.

* **Frontend:**

  * **JavaScript** – Manipulação do DOM e consumo da API.
  * **HTML/CSS** – Estruturação visual e estilização responsiva das telas.

* **Integração:**

  * Comunicação assíncrona entre frontend e backend utilizando requisições HTTP via **fetch API**.

---


## 👤 Contribuições Pessoais


### Como Desenvolvedor
1. **Crud de perfil de usuario**:
   - Criado todas as operações em relação ao crud do perfil de usuario.
   - Desenvolvida a lógica de abstração para realizar operações de **CRUD** no "banco" de dados.


```
class profile_repository(object):
    _apiContext: ApiContext = ApiContext()
    def __init__(self) -> None:
        pass
    def get(self):
        return self._apiContext.user_table.get_all()
    def busca_id_profile(self,id):
        return self._apiContext.profile_table.get(id)
    def post_profile(self, objectPost):
        self._apiContext.profile_table.begin_transaction()
        self._apiContext.profile_table.insert(objectPost)
        self._apiContext.profile_table.commit()
    def put_profile(self, objectPut):
        self._apiContext.profile_table.begin_transaction()
        self._apiContext.profile_table.commit()
        self._apiContext.user_table.begin_transaction()
        self._apiContext.user_table.update(objectPut)
        self._apiContext.user_table.commit()
    def delete_id_usuario(self, id:int):
        self._apiContext.user_table.begin_transaction()
        self._apiContext.user_table.delete(id)
        self._apiContext.user_table.commit()
```

A classe profile_repository foi construída para encapsular as operações de leitura, escrita, atualização e exclusão de perfis e usuários em um sistema

2. **Implementação de validação para verificar a que turma um usuario pertencia**:
   - Desenvolvimento completo do endpoint e comunicação com banco:


 ```
 def create(self, model: grupo_model):

        grupoBd = self._modelToBd(model)
        times_em_grupo = self._teamsRepository.findTeamByGroup(grupoBd.id)
        grupo = self._grupo_repository.busca_id_grupo(grupoBd.id)
        grupo_id=self._grupo_repository.get(grupo.get('id'))


        for time in times_em_grupo:
            if time == grupo_id:
                raise Exception("Este time ja esta associado a este grupo");

        item = self._grupo_repository.post_grupo(grupoBd)
        model.id = item.id;
        self.updateTeam(model);
 ```

Percorrido o grupo eu consigo validar se ja pertence um time naquele grupo que correpondam ao usuario, garantindo que não haja duplicidade de times dentro do grupo
 

3. **Implementação da listagem de usuario**:
   - Desenvolvimento de endpoint para listagem de usuario.

   Detalhes

```
class usuario_services(object):
    _user_repository:user_repository = user_repository()
    def __init__(self):
        pass;
    def buscar_usuario(self):
        return self._user_repository.get()

```
   
5. **Implementação de roteamento**:
   - Desenvolvimento de rotas para endpoint.


```
   from fastapi import APIRouter
from ..controllers import usuario_controler, test_controller, autenticacao_controller

router = APIRouter()
router.include_router(test_controller.router)
router.include_router(autenticacao_controller.router)
router.include_router(usuario_controler.router)

```

---

## 🛠 Hard Skills

| Tecnologia / Metodologia | Nível de Proficiência             |
| ------------------------ | --------------------------------- |
| **Python**               | ★★★★★★★★★★ (Avançado)             |
| **HTML/CSS**             | ★★★☆☆☆☆☆☆☆ (Básico-Intermediário) |
| **JavaScript**           | ★★★☆☆☆☆☆☆☆ (Básico-Intermediário) |
| **FastAPI**              | ★★★★★★★★★★ (Avançado)             |
| **Scrum**                | ★★★★★★★★★★ (Avançado)             |

### Justificativas para Hard Skills

| Tecnologia / Metodologia | Justificativa                                                                                                  |
| ------------------------ | -------------------------------------------------------------------------------------------------------------- |
| **Python**               | Proficiência avançada no desenvolvimento de aplicações backend, automação de processos e análise de dados.     |
| **HTML/CSS**             | Conhecimento sólido em estruturação e estilização de páginas, com foco em responsividade e usabilidade básica. |
| **JavaScript**           | Experiência inicial, suficiente para manipulação do DOM e integração com APIs REST no frontend.                |
| **FastAPI**              | Expertise no desenvolvimento de APIs RESTful escaláveis e performáticas, com validação robusta de dados.       |
| **Scrum**                | Vivência prática em gerenciamento ágil de projetos, facilitando entregas incrementais e trabalho colaborativo. |

---

## 💡 Soft Skills

| Habilidade                 | Nível de Desenvolvimento |
| -------------------------- | ------------------------ |
| **Comunicação**            | ★★★★★★★★★★ (Excelente)   |
| **Trabalho em Equipe**     | ★★★★★★★★★☆ (Muito Bom)   |
| **Resolução de Problemas** | ★★★★★★★★★★ (Excelente)   |
| **Responsabilidade**       | ★★★★★★★★★★ (Excelente)   |

### Justificativas para Soft Skills

| Habilidade                 | Justificativa                                                                                                                        |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **Comunicação**            | Capacidade notável para expressar ideias de forma clara e objetiva, facilitando o entendimento em ambientes técnicos e não técnicos. |
| **Trabalho em Equipe**     | Experiência sólida em colaboração multidisciplinar, promovendo um ambiente de trabalho harmonioso e produtivo.                       |
| **Resolução de Problemas** | Aptidão para identificar desafios complexos e implementar soluções inovadoras e eficazes.                                            |
| **Responsabilidade**       | Comprometimento consistente com prazos e qualidade, garantindo entregas confiáveis e alinhadas às expectativas.                      |

---

</details>




### 2023 - Primeiro Semestre
- [Link para o README do Projeto 2º Semestre](https://github.com/api-2-sem/api)
<details>
<summary><b> 2023-1 </b></summary>


  # 🕒 Projeto de Sistema Desktop para Gestão de Horas Extras – Parceira **2RP**

## 🏢 Empresa Parceira: 2RP

A empresa parceira escolhida foi a **2RP**, que atua no setor de **análise de transações financeiras** e **inteligência de dados**, com foco na geração de **insights estratégicos** para aprimorar a experiência de seus clientes e impulsionar a tomada de decisão baseada em dados.

---

## 📌 Desafio

A 2RP identificou a necessidade de desenvolver uma aplicação desktop para a **gestão eficiente das horas extras de seus colaboradores**, com diferentes funcionalidades voltadas aos perfis de **usuários comuns, gestores e administradores**.

### Principais Requisitos:

* Colaboradores devem poder registrar e consultar suas horas extras **em tempo real**.
* Gestores e administradores devem ser capazes de:

  * **Gerenciar acessos** com base em perfis de usuário.
  * **Personalizar parâmetros do sistema**, como:

    * Horário de início do período noturno.
    * Valores atribuídos às horas extras (comum e noturna).
  * **Extrair relatórios gerenciais e analíticos** com filtros por data, usuário, centro de custo, entre outros.

---

## 💡 Solução Desenvolvida

Foi criada uma aplicação desktop e segura, com funcionalidades específicas para cada tipo de usuário.

### 🔒 **Administradores**

* Acesso completo ao sistema com funcionalidades de:

  * **CRUD** de usuários, centros de resultado e clientes.
  * Configuração de parâmetros do sistema:

    * Valor da hora extra comum e noturna.
    * Horário de início e término do período noturno.
  * **Aprovação e reprovação** de lançamentos realizados por colaboradores.
  * Geração de **relatórios gerenciais detalhados**, com exportação em múltiplos formatos.

### 👨‍💼 **Gestores**

* Lançamento de horas extras para membros de sua equipe.
* Visualização e análise em tempo real das horas lançadas por colaboradores sob sua gestão.
* Acesso a relatórios específicos com filtros personalizados.

### 👷 **Usuários (Colaboradores)**

* Lançamento individual das horas extras realizadas.
* Acompanhamento diário e mensal das horas extras acumuladas.
* Visualização de status dos lançamentos (pendente, aprovado ou reprovado).

---

## ⚙️ Tecnologias Utilizadas

* **Frontend:** Javafx
* **Backend:** Java 
* **Banco de Dados:** MySQL
* **Controle de Versão:** Git e GitHub
* **Metodologia:** Desenvolvimento ágil com foco em entregas modulares e testes contínuos

---

## 👨‍💻 Contribuições Pessoais

Durante o projeto, atuei diretamente nas seguintes frentes:

* Desenvolvimento e integração dos módulos de autenticação, lançamento e validação de horas.
* Implementação das regras de negócio para cálculo das horas extras com base em faixas horárias.
* Construção dos componentes de relatório e filtros personalizados por perfil.
* Integração completa entre frontend e backend via API REST.
* Versionamento de código e organização da estrutura do repositório.

---

## 🧠 Habilidades Desenvolvidas

### Técnicas (Hard Skills)

* Programação com **Java** e **JavaFx**.
* Consumo e criação de **APIs RESTful**.
* Modelagem e manipulação de dados em **MySQL**.
* Versionamento e colaboração com **Git/GitHub**.

### Interpessoais (Soft Skills)

* Colaboração em equipe multidisciplinar.
* Adaptação a requisitos dinâmicos.
* Comunicação efetiva e organização no trabalho em equipe.
* Resolução ágil de problemas técnicos.

---

## GitHub do Projeto  
- [Repositório no GitHub](https://github.com/api-2-sem/api)  

---

## 🛠 Tecnologias Utilizadas

### **Java**  
- **Linguagem principal** do projeto.  
- Utilizada para manipulação de dados e criação de eventos atrelados à exibição de informações.  

### **CSS**  
- Utilizado para estilização das telas.  
- Escolhido pela integração com o **SceneBuilder**, facilitando a criação de layouts atrativos.  

### **MySQL**  
- Escolhido pela sua confiabilidade, desempenho e facilidade de uso.  
- Responsável por garantir a **persistência** e **integridade dos dados** do sistema.  

---

## 👤 Contribuições Pessoais


Nesse projeto atuei como desenvolvedor. Como desenvolvedor, minhas contribuições foram:

Detalhes 

```
public class Login{
	private String email;
	private String password;
	
	public Login(String email, String password) {
		this.email = email;
		this.password = password;
	}
	
	public boolean auth(String email,String password) {
		Login login = new Login(email, password);
		return this.email.equals(email) && this.password.equals(password);
	}
}
```

A classe Login possui dois atributos privados: email e password, que armazenam respectivamente o e-mail e a senha do usuário. Ao instanciar a classe através do construtor Login(String email, String password), esses dois atributos são inicializados com os valores fornecidos.

O método auth(String email, String password) serve para verificar se os dados fornecidos coincidem com os armazenados. Ele cria um novo objeto Login com os parâmetros recebidos (embora essa instância não seja realmente usada) e retorna true apenas se o e-mail e a senha passados como argumento forem exatamente iguais aos armazenados no objeto original (this.email e this.password). Caso contrário, retorna false


Fui encarregado de criar a tela de login no SceneBuilder, utilizando para isso CSS e algumas imagens padrões da empresa parceira. Nessa mesma tela foi implementado regras de acesso ao sistema.

Detalhes

![image](https://github.com/user-attachments/assets/08436240-9df9-4d58-b94c-ccac1a7b34f4)

Como email e senha

Desenvolvimento de feedbacks alertando o usuario sobre sucesso de operacao 

```
public class MensagemRetorno {	
	public MensagemRetorno() {
		super();
	}

	public static void sucessoCadastro() {
		sucesso("Cadastro efetuado com sucesso");
	}

	public static void sucesso(String message) {
		Alert alert = new Alert(AlertType.INFORMATION);
		alert.setContentText(message);
		alert.show();
	}
	
	public static void erroCadastro() {
		erro("Não foi possível efetuar o cadastro");
	}

	public static void erro(String message) {
		Alert alert = new Alert(AlertType.ERROR);
		alert.setContentText(message);
		alert.show();
	}
}
```

A classe MensagemRetorno tem como principal objetivo centralizar e padronizar a exibição de mensagens para o usuário, especialmente em aplicações com interface gráfica desenvolvidas em JavaFX. Por meio de métodos estáticos, ela permite mostrar mensagens de sucesso ou erro utilizando caixas de diálogo (Alert), o que contribui para uma melhor experiência do usuário


Estabeleciomento de rota para tela de cadastro de usuario 

 ```
 @FXML
    void irControleUsuario(MouseEvent event) {
        changeScene("/view/CadastroUsuario.fxml");
    }
 ```

Detalhes 

![image](https://github.com/user-attachments/assets/963fb8b8-b836-4a4f-8ee0-13aecba109c9)


Uma maneira de estabelecer navegacao no sistema

Foi desenvolvido um dashboard 


```

    @FXML
    protected void initialize() {
        ExtratoHoraDAO extratoHoraDAO;


        ObservableList<PieChart.Data> pieChartData = FXCollections.observableArrayList();

        int qtdAprovada = extratoHoraDAO.qtdHoraAprovada();
        if (qtdAprovada > 0) {
            pieChartData.add(new PieChart.Data("Aprovado", qtdAprovada));
        }

        int qtdReprovada = extratoHoraDAO.qtdHoraReprovada();
        if (qtdReprovada > 0) {
            pieChartData.add(new PieChart.Data("Reprovado", qtdReprovada));
        }

        dashboard.setData(pieChartData);
    }
```

Se houver algum aprovado ele entra na seção de aprovado caso nao entra no reporvado e 

Detalhes


![image](https://github.com/user-attachments/assets/7cb06e1a-8040-4770-953e-7c788d2f10e0)

Como podem ver o colaborador pode contabalizar as horas que foi aprovada e reprovada no sistema

Desenvolvimento de regra para pegar horas reprovadas no sistema

```
 //select para pegar horas reaprovada 
    public int qtdHoraReprovada() {
    	try {
    		String sql = "FROM extrato_hora SELECT Id_Etapa_Extrato";
    		executarQuery(sql);
    		return executarQuery(sql);
    	}catch(Exception e) {
    		e.addSuppressed(e);
    	}
}
```


## 🛠 Hard Skills

| Tecnologia / Metodologia      | Nível de Proficiência      |
| ----------------------------- | -------------------------- |
| **SQL**                       | ★★★★★★★★☆☆☆ (Avançado)     |
| **MySQL**                     | ★★★★★★★☆☆☆ (Intermediário) |
| **SceneBuilder / HTML / CSS** | ★★★★★★★★☆☆☆ (Avançado)     |
| **Java**                      | ★★★★★★★☆☆☆ (Intermediário) |
| **Scrum**                     | ★★★★☆☆☆☆☆☆ (Básico)        |

### 🔎 Justificativa das Hard Skills

| Tecnologia / Metodologia      | Justificativa                                                                                                 |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------- |
| **SQL**                       | Experiência sólida em manipulação de dados, criação de views e queries complexas para geração de indicadores. |
| **MySQL**                     | Aplicação prática do SGBD no projeto, com foco em performance, normalização e consistência dos dados.         |
| **SceneBuilder / HTML / CSS** | Criação de interfaces funcionais e bem estruturadas, com atenção à experiência do usuário e responsividade.   |
| **Java**                      | Desenvolvimento das funcionalidades principais do backend utilizando orientação a objetos.                    |
| **Scrum**                     | Participação em reuniões de planejamento e revisão de sprint, com uso de artefatos como backlog e daily.      |

---

## 💡 Soft Skills

| Habilidade                 | Nível de Desenvolvimento |
| -------------------------- | ------------------------ |
| **Comunicação**            | ★★★★★★☆☆☆☆ (Moderado)    |
| **Trabalho em Equipe**     | ★★★★★★★☆☆☆ (Bom)         |
| **Resolução de Problemas** | ★★★★★★★★★☆ (Muito Bom)   |
| **Responsabilidade**       | ★★★★★★★☆☆☆ (Bom)         |

### 🔎 Justificativa das Soft Skills

| Habilidade                 | Justificativa                                                                                                                        |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **Comunicação**            | Atuei de forma clara ao expor ideias e dúvidas, principalmente ao sugerir melhorias e buscar ajuda para resolver problemas técnicos. |
| **Trabalho em Equipe**     | Contribuí ativamente com o grupo, especialmente em momentos de aprendizado coletivo e colaboração técnica.                           |
| **Resolução de Problemas** | Demonstrei eficiência na identificação e resolução de problemas técnicos, especialmente em SQL e integração com o backend.           |
| **Responsabilidade**       | Entreguei todas as demandas sob minha responsabilidade dentro do prazo, com qualidade e comprometimento.                             |

---

</details>


### 2023 - Segundo Semestre
- [Link para o README do Projeto 3º Semestre](https://github.com/api-3-sem/api)

<details>
<summary><b> 2023-2 </b></summary>

# ⏱️ Projeto de Sistema Web para Gestão de Horas Extras – **2RP**

## 🏢 Empresa Parceira: 2RP

A empresa parceira deste projeto é a **2RP**, especializada em **análise de transações financeiras** e **processamento de dados** com foco na geração de **insights estratégicos** para aprimorar a experiência e a eficiência operacional de seus clientes.

---

## 📌 Problema Identificado

A 2RP identificou a necessidade de um sistema digital para **otimizar a gestão de horas extras**, tanto do ponto de vista operacional quanto gerencial.

Os principais desafios mapeados foram:

### 👤 **Para Usuários (Colaboradores)**

* Registrar horas extras de forma prática e segura.
* Visualizar em tempo real o total de horas acumuladas.

### 👥 **Para Gestores**

* Lançar horas extras de suas equipes.
* Acompanhar os registros em tempo real.
* Gerar relatórios analíticos de produtividade.

### 🛠️ **Para Administradores**

* Gerenciar acessos e permissões.
* Personalizar regras do sistema (como valores de hora extra e horário noturno).
* Validar, aprovar ou reprovar lançamentos de horas.
* Extrair relatórios globais detalhados para auditoria e tomada de decisão.

---

## 💡 Solução Desenvolvida

Com base nas necessidades levantadas, foi desenvolvido um **sistema web responsivo e modular**, com foco em usabilidade, segurança e escalabilidade.

### 🧑‍💼 **Módulo do Administrador**

* Gestão completa de:

  * Usuários.
  * Clientes.
  * Centros de resultado.
* Parametrização do sistema:

  * Definição personalizada de faixas de horário noturno.
  * Estabelecimento dos valores de hora extra (normal e noturna).
* Validação de lançamentos:

  * Aprovação ou reprovação de horas extras enviadas pelos colaboradores.
* Relatórios gerenciais detalhados, exportáveis para auditoria.

### 👨‍💼 **Módulo do Gestor**

* Lançamento manual de horas extras para membros da equipe.
* Acompanhamento em tempo real do desempenho por colaborador.
* Geração de relatórios filtrados por período, colaborador ou centro de resultado.

### 👷 **Módulo do Usuário (Colaborador)**

* Registro individual de horas extras trabalhadas.
* Visualização em tempo real das horas acumuladas no mês.
* Histórico de aprovações e pendências.

---


## GitHub do projeto

- [Repositório no GitHub](https://github.com/api-3sem-pixel-api/api)

---

## 🛠 Tecnologias Utilizadas

### **Java**  
- Utilizado como linguagem principal para desenvolvimento do backend. Sua robustez e portabilidade foram essenciais para a construção de um sistema confiável.  

### **Spring Framework**  
- Forneceu suporte para injeção de dependências, controle transacional e segurança, simplificando o desenvolvimento e garantindo a escalabilidade do sistema.  

### **Maven**  
- Facilitou o gerenciamento de dependências e automação de tarefas, garantindo consistência no ambiente de desenvolvimento.  

### **Vue.js**  
- Framework utilizado para o frontend, permitindo o desenvolvimento de interfaces interativas, modernas e responsivas.  

### **MySQL**  
- Sistema de gerenciamento de banco de dados escolhido por sua confiabilidade e desempenho, garantindo a persistência e integridade dos dados.  

---


## 👤 Contribuições Pessoais

Durante o projeto, atuei como **desenvolvedor full stack**, contribuindo significativamente para a implementação de diversas áreas do sistema. Minhas responsabilidades incluíram tanto o desenvolvimento backend quanto frontend, trabalhando na integração de funcionalidades críticas do sistema.

Além disso, assumi a função de **Scrum Master**, sendo responsável pelo gerenciamento do time, acompanhamento do progresso das sprints e lançamento do gráfico de **burndown**. Também cuidei da **documentação da proposta de solução**, garantindo que todas as etapas do projeto estivessem devidamente registradas e compreendidas pela equipe.

### **Correção no Mapeamento de DTO**

Realizei a implementação do mapeamento de **DTOs (Data Transfer Objects)** para incluir a relação entre o cliente ativo e inativo. O desenvolvimento foi importante para garantir que a comunicação entre as camadas do sistema refletisse corretamente o estado dos clientes no banco de dados.
```java
public record DadosCadastroCliente(String razaoSocialCliente, String cnpjCliente, boolean ativo) {
}
```
Com o DTO e o modelo de dados definidos, criei o modelo Cliente, que facilita a comunicação entre a aplicação e o banco de dados. Esse modelo é responsável por mapear as tabelas correspondentes no banco de dados e garantir que os dados sejam manipulados de forma eficiente.
 

```
@Table(name = "Cliente")
@Entity(name = "Cliente")
@Getter
@Setter
@AllArgsConstructor
@NoArgsConstructor
public class Cliente {
	
	@Id
	@GeneratedValue(strategy = GenerationType.IDENTITY)
	private Long id;
	@Column(name = "Razao_Social")
	private String razaoSocial;
	private String cnpj;
	private boolean ativo;
	
	@JsonIgnore
	@OneToMany(mappedBy = "cliente")
	private List<LancamentoHoras>lancamento;
	
	public Cliente(Long idCliente) {
		this.id = idCliente;
	}
	
	public Cliente(DadosCadastroCliente dados) {
		this.razaoSocial = dados.razaoSocialCliente();
		this.cnpj = dados.cnpjCliente();
		this.ativo = true;
	}  
}
```

Desenvolvi o controle para exibição das telas de inativação de clientes, incluindo toda a funcionalidade de visualização de clientes . Isso envolveu a comunicação HTTP, criação do layout e a vinculação com o framework VUE. Além de necessitar do uso das diretivas do vue, com o  v-for.

```
<template>
  <Cliente @update-table="loadAllcliente"></Cliente>
  <div class="row">
    <table class="table table-responsive no-wrap-table">
      <thead>
        <tr>
          <th scope="col" class="text-left">Razão Social</th>
          <th scope="col" class="text-left">Cnpj</th>
        
          <th scope="col" class="text-center">Status</th>
          <th scope="col" class="text-center">Ações</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(client, index) in clientes" :key="index">
      
         
          <td>{{ client['razaoSocialCliente'] }}</td>
          <td>{{ client['cnpjCliente'] }}</td>
          <td class="text-center d-flex" style="justify-content: center;"  > <div 
          class="pill approved text-center text-wrap" 
          :class="{
            approved: client['ativo'] == true,
        }" > 
            Ativo 
        </div></td>
          <td class="text-center">
            <button class="btn btn-link"><i class="fa fa-pencil" aria-hidden="true"></i></button>

        <button class="btn btn-link" @click="inativarCliente(client['id'])"><i class="fa fa-trash"  aria-hidden="true" ></i></button>

        
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
```

Desenvolvi uma função para inativar clientes, permitindo a comunicação com a API backend por meio de uma requisição HTTP DELETE, acionada pelo evento de clique no botão do componente. Reproduzindo fielmente o design solicitado pelo nosso UI no Figma e implementando a integração completa entre o backend e o frontend

```
async inativarCliente(clienteId: number) {
  const cliente = this.clientes.find((cliente) => cliente.id === clienteId);
  console.log(cliente);
  if (cliente) {
    if (cliente.ativo) {
      try {
        await http.delete(`/cliente/${clienteId}`);
        cliente.ativo = false;
        alert('Cliente inativado com sucesso');
      } catch (error) {
        alert('Erro ao inativar o cliente. Tente novamente mais tarde.');
      }
    } else {
      alert('O cliente já está inativo');
    }
  } else {
    alert('Cliente não encontrado');
  }
}

  },
});
```

Detalhes

![image](https://github.com/user-attachments/assets/be565bbd-69cf-4a02-9796-eb390e3f27b2)


Foram desenvolvidos os métodos *GET*, *UPDATE* e *POST* para o usuário na interface do front-end, juntamente com a definição de um template para cadastro de usuários.

```


<template>
  <div id="cadastro-user-modal" class="r-modal">
    <div class="r-modal-content">
      <div class="modal-header d-flex align-items-baseline">
        <h4>Cadastro de Usuário</h4>
        <span class="close" @click="close">&times;</span>
      </div>
      <div class="modal-body">
        <div class="row">
          <div class="col-12">
            <div class="form-group">
              <label for="nome">Nome</label>
              <input type="text" class="form-control" id="nome" v-model="nome" />
            </div>
          </div>
        </div>

        <div class="row">
          <div class="col-12">
            <div class="form-group">
              <label for="telefone">Telefone</label>
              <input type="text" class="form-control" id="telefone" v-model="telefone" />
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-12">
            <div class="form-group">
              <label for="email">Email</label>
              <input type="text" class="form-control" id="email" v-model="email" />
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-12">
            <div class="form-group">
              <label for="cpf">CPF</label>
              <input type="text" class="form-control" id="cpf" v-model="cpf" />
            </div>
          </div>
        </div>

        <div class="row">
          <div class="col-12">
            <div class="form-group">
              <label for="funcao">Função</label>
              <select class="form-select" id="funcao" v-model="funcao">
                <option value="Colaborador">Colaborador</option>
                <option value="Administrador">Administrador</option>
                <option value="Gestor">Gestor</option>
              </select>
            </div>
          </div>
        </div>

        <div class="row mt-4">
          <div class="col">
            <button type="button" @click="save" class="btn btn-success">Salvar</button>
            <button type="button" @click="close" class="btn btn-link r-ml-2">Cancelar</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
 ```

Detalhes

Listagem de usuarios e demais opções endpoint

![image](https://github.com/user-attachments/assets/90c2920f-a8d1-4db8-b384-e2f325772f8f)

Cadastro de usuario

![image](https://github.com/user-attachments/assets/b45442f3-4090-4f70-b678-93b3b04c6f24)


Criei referente as operações do CRUD, os metodos de update e e read podendo visualizar informações referente ao usuario e atualizar essas mesma informções


 ``` 
  <div class="row">
    <table class="table table-responsive no-wrap-table">
      <thead>
        <tr>
          <th scope="col" class="text-left">Nome</th>
          <th scope="col" class="text-left">Email</th>
          <th scope="col" class="text-left">Telefone</th>
          <th scope="col" class="text-left">CPF</th>
          <th scope="col" class="text-center">Função</th>
          <th scope="col" class="text-center">Ações</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(usuario, index) in usuarios" :key="index">
          <td>{{ usuario['nome'] }}</td>
          <td>{{ usuario['email'] }}</td>
          <td>{{ usuario['telefone'] }}</td>
          <td>{{ usuario['cpf'] }}</td>
          <td>{{ enumUser[usuario['funcao']] }}</td>
          <td class="text-center">
            <button class="btn btn-link" @click="updateUser(usuario.id)">
              <i class="fa fa-pencil" aria-hidden="true"></i>
            </button>
            <button class="btn btn-link" @click="excludedUser(index)">
              <i class="fa fa-trash" aria-hidden="true"></i>
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>

updateUser(userId: number) {
      this.editUserId = userId;
      var modal = document.getElementById("update-user-modal");
      if (modal) {
        modal.style.display = "block";
      } else {
        console.error("Elemento não encontrado no DOM.");
      }
    },

    async updateUserDetails(updatedUser: any) {
      try {
        await http.put(`/usuario/${this.editUserId}`, updatedUser);

        // Atualize os dados do usuário no array this.usuarios
        const userIndex = this.usuarios.findIndex(u => u.id === this.editUserId);
        if (userIndex !== -1) {
          this.usuarios[userIndex] = updatedUser;
        }

        this.closeUpdateModal(); 
      } catch (error) {
        alert('Erro ao atualizar o usuário. Tente novamente mais tarde.');
      }
    },
    closeUpdateModal() {
      this.editUserId = null; 
      var modal = document.getElementById("update-user-modal");
      if (modal) {
        modal.style.display = "none";
      }
    },


 ``` 

Desenvolvimento da tela de login e ação de entrar no sistema


Implementação da tela de login e do método de autenticação, incluindo a ação de login. A tela não apresentava grande complexidade técnica, o que permitiu concentrar esforços na estilização e na melhoria da experiência do usuário

 ``` 
<template>
  <div class="login-container">
    <div class="login-box-container">
      <div class="login-box">
        <h2>Login</h2>
        <input type="text" placeholder="Usuário" v-model="username" />
        <input type="password" placeholder="Senha" v-model="password" />
        <button @click="login">Entrar</button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import  http  from "@/services/http";
import { useAuth } from '@/stores/auth';

export default defineComponent({
  data() {
    return {
      username: '',
      password: '',
    };
  },
  methods: {
    async login() {
      const auth = useAuth();

      try {
        const user = {
          email: 'emilly94@ramos.com',
          password: '123',
        };

        const { data } = await http.post('/auth', user);
        auth.setToken(data.token);
        auth.setUser(data.user);
        auth.setIsAuth(true);
      } catch (error) {
        console.log(error);
      }
    },
  },
});
</script>

<style scoped>
.login-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.login-box-container {
  text-align: center;
  background: linear-gradient(to bottom right, #0041d8, #7cbeeb);
}

.login-box {
  background: linear-gradient(to bottom right, #0041d8, #7cbeeb);
  border-radius: 10px;
  padding: 20px;
  margin: 10px 0 40px;

  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  max-width: 500px;
  width: 100%;
}

.login-box h2 {
  margin-bottom: 20px;
}

.login-box input {
  width: 80%;
  max-width: 80%;
  padding: 10px;
  margin: 10px 0 40px;

  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
}

.login-box button {
  width: 100%;
  max-width: 50%;
  padding: 10px;
  background: #ffffff;
  color: #d3baba;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  border: none;
  border-radius: 5px;
  font-size: 18px;
  cursor: pointer;
  margin-top: 40px;
}
</style>
```


Detalhes 


![image](https://github.com/user-attachments/assets/ce8bc3ca-b563-4fed-a4dd-cd063cfb6332)


---

## **Contribuições como Scrum Master**

Durante o desenvolvimento de um sistema web para gestão de tarefas acadêmicas, o cliente — um grupo de alunos e professores — buscava uma solução eficiente para organizar e acompanhar atividades, prazos e responsabilidades de forma colaborativa. O desafio principal era garantir a organização das entregas em um curto espaço de tempo, promovendo integração entre os membros e mantendo a qualidade das entregas, mesmo com diferentes níveis de experiência técnica na equipe.

Como **Scrum Master**, atuei como facilitador do processo de desenvolvimento ágil, com foco em garantir que a equipe seguisse os princípios do **Scrum** de forma disciplinada e produtiva. Minhas principais contribuições envolveram:

* **Planejamento e organização das sprints**, definindo claramente os objetivos de cada ciclo de entrega e promovendo reuniões de planejamento e review com o time.
* **Documentação das tarefas no ClickUp**, o que proporcionou total visibilidade para todos os membros da equipe e permitiu que as atividades fossem monitoradas e atualizadas com clareza.
* **Criação e análise de burndown charts**, que ajudaram a identificar gargalos e ajustar o ritmo de trabalho conforme necessário.
* **Mediação de conflitos e facilitação da comunicação entre membros da equipe**, promovendo um ambiente de cooperação e responsabilidade mútua.
* **Aplicação de cerimônias ágeis** (daily meetings, sprint planning e retrospectivas), aumentando a transparência e a capacidade de adaptação diante de mudanças de escopo.

Essas atividades exigiram o uso efetivo de **hard skills**, como o domínio de ferramentas de gestão ágil, conhecimento de **metodologias ágeis (Scrum)**, e capacidade técnica para dialogar com desenvolvedores sobre **APIs REST**, **HTML/CSS**, e **Vue.js**. Paralelamente, foi essencial o uso de **soft skills**, especialmente **comunicação**, **trabalho em equipe**, **resolução de problemas** e **responsabilidade** para conduzir a equipe de forma colaborativa, focada em resultados.

---

## **Hard Skills**

| Tecnologia/Metodologia | Classificação |
| ---------------------- | ------------- |
| **SQL**                | ★★★★★★☆☆☆☆☆   |
| **MySQL**              | ★★★★☆☆☆☆☆☆    |
| **HTML/CSS**           | ★★★★★★★☆☆☆    |
| **Vue**                | ★★★★★★★☆☆☆    |
| **REST**               | ★★★★★★★☆☆☆    |
| **Scrum**              | ★★★★★★★☆☆☆    |
| **UX/UI Design**       | ★★★★★☆☆☆☆☆    |

### Justificativa

| Tecnologia/Metodologia | Justificativa                                                                                             |
| ---------------------- | --------------------------------------------------------------------------------------------------------- |
| **SQL/MySQL**          | Conhecimento funcional na criação de tabelas e execução de queries simples para apoio ao desenvolvimento. |
| **HTML/CSS**           | Desenvolvimento de layouts para interfaces do sistema com foco em responsividade e usabilidade.           |
| **Vue.js**             | Criação e gerenciamento de componentes dinâmicos e reativos da interface do sistema.                      |
| **REST**               | Apoio na implementação e integração de endpoints RESTful no projeto.                                      |
| **Scrum**              | Atuação direta como facilitador no uso da metodologia, aplicando práticas de planejamento e entrega ágil. |
| **UX/UI Design**       | Criação de wireframes e ajustes de interface baseados no feedback dos usuários finais.                    |

---

## **Soft Skills**

| Habilidade                 | Classificação |
| -------------------------- | ------------- |
| **Comunicação**            | ★★★★★★☆☆☆☆☆   |
| **Trabalho em Equipe**     | ★★★★☆☆☆☆☆☆    |
| **Resolução de Problemas** | ★★★★★★★☆☆☆    |
| **Responsabilidade**       | ★★★★★★☆☆☆☆☆   |

### Justificativa

| Habilidade                 | Justificativa                                                                                              |
| -------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Comunicação**            | Facilitou a compreensão entre membros técnicos e não técnicos, essencial para manter todos alinhados.      |
| **Trabalho em Equipe**     | Participação ativa em decisões do grupo, ajudando na integração entre membros com diferentes experiências. |
| **Resolução de Problemas** | Condução de decisões rápidas durante imprevistos nas sprints, como replanejamento de tarefas prioritárias. |
| **Responsabilidade**       | Garantia de que prazos e entregas fossem cumpridos, mantendo o comprometimento com a qualidade.            |

---


</details>

### 2024 - Primeiro Semestre
- [Link para o README do Projeto 4º Semestre](https://github.com/api-4-sem/api)


<details>
<summary><b> 2024-1 </b></summary>

# 📈 Projeto de Sistema de Acompanhamento de Parceiros - **Oracle**

## 🏢 Empresa Parceira: Oracle

A empresa parceira deste projeto é a **Oracle**, uma das líderes globais em tecnologia da informação.

### 🌐 Atuação da Oracle

A **Oracle** é uma multinacional especializada em **tecnologia em nuvem**, oferecendo **infraestrutura de computação, software empresarial e banco de dados** para organizações em todo o mundo. Seu objetivo é ajudar empresas a inovar, operar com mais eficiência e se tornarem mais resilientes e sustentáveis.

O impacto da Oracle vai além do setor corporativo. Suas soluções também apoiam **governos, ONGs e instituições de pesquisa científica e médica**. De pequenas empresas a grandes corporações, milhões de pessoas utilizam as ferramentas da Oracle para:

* Automatizar cadeias de suprimentos;
* Otimizar a gestão de recursos humanos;
* Planejar financeiramente com agilidade;
* Transformar dados em decisões estratégicas.

---

## 📌 Problema Identificado

A Oracle apresentou o desafio de desenvolver um sistema para **monitoramento e gestão de parceiros**, com foco em **capacitação e desempenho regional**.

O sistema precisava contemplar:

* 📍 **Monitoramento da distribuição percentual de parceiros por estado**;
* 🎓 **Acompanhamento da taxa de conclusão dos cursos de capacitação por parceiro**;
* ⏳ **Gestão da validade dos cursos, com alerta para vencimentos próximos**.

---

## 💡 Solução Desenvolvida

Para atender às necessidades da Oracle, foi projetado e implementado um **sistema inteligente e interativo**, com as seguintes funcionalidades:

### 🧑‍💼 Gerenciamento de Usuários e Parceiros

* Cadastro e gerenciamento de **empresas parceiras**, usuários e suas respectivas **trilhas de capacitação**.

### 📊 Dashboard Analítico

* Visualização **em tempo real** da **distribuição geográfica de parceiros**, com mapas e gráficos.
* Indicadores de **taxas de conclusão de cursos** e **nível de engajamento por parceiro**.

### 🔔 Notificações Inteligentes

* Sistema automatizado de **alertas e notificações**, informando parceiros sobre a **proximidade do vencimento dos cursos**.

### 🔐 Controle de Acesso

* Módulo de permissões com diferentes níveis de acesso, garantindo segurança e confidencialidade dos dados.

---

## GitHub do projeto

- [Repositório no GitHub](https://github.com/api-4-sem/api)

---


## 🛠 Tecnologias Utilizadas

### Backend
- **Java**: Linguagem utilizada no backend, amplamente usada em aplicações web e mobile. Escolhida pela robustez e por ser ensinada na FATEC.
- **Spring Boot**: Framework utilizado para:
  - Configuração e estruturação do projeto.
  - Criação de endpoints.
  - Persistência de dados.
  - Segurança da API.

### Frontend
- **TypeScript**: Substituto ao JavaScript, oferecendo:
  - Maior escalabilidade.
  - Melhor manutenção e depuração do código devido à tipagem estática.
- **Vue**: Framework frontend escolhido por sua simplicidade e facilidade de manutenção, com suporte para componentes reutilizáveis.

### Banco de Dados
- **MySQL**: Banco de dados escolhido pela confiabilidade, performance e facilidade de uso, garantindo a persistência e a integridade dos dados do sistema.

---

## 👤 Contribuições Pessoais

### 🔹 Como Product Owner
- **Organização e Criação do Backlog**:
  - Criação e organização de todo o backlog do projeto, incluindo:
    - **User Stories.**
    - Priorização.
    - Alinhamento com o cliente.
  - Estruturação do backlog com **Épicos**, **Features** e organização das **Sprints**.

---

### 🔹 Como Desenvolvedor

#### Endpoint para Criação e Exibição de Empresas
Desenvolvi o endpoint responsável pela criação e exibição da entidade **Empresa**, seguindo os passos abaixo:

1. **Criação do Repository**: 
   Definição de uma interface para mapeamento e carregamento de entidades.


 ```
public interface EmpresaJpaRepository extends JpaRepository<Empresa, Long>, EmpresaRepository {

    @Query(value = """
                    select e.id as id, e.codigo as codigo, e.nome as nome, e.cidade as cidade, e.pais as pais, 
                    e.adminNome as adminNome, e.adminEmail as adminEmail 
                    from Empresa e""")
    List<EmpresaProjection> carregar();
}
 ```


Criação do Projection: Mapeamento dos campos da entidade Empresa para atender à camada de apresentação.


 ```
package br.gov.sp.fatec.apipixel.core.domain.projection;

public interface EmpresaProjection {
    Long getId();
    String getNome();
    String getAdminEmail();
    String getAdminNome();
    String getPais();
    String getCidade();
    Long getCodigo();
}
 ```

Definição da Entidade Empresa: Mapeei a classe Empresa para persistência e utilizei métodos estáticos para facilitar a conversão entre os comandos e a entidade.

```

@Getter
@Setter
@AllArgsConstructor
@NoArgsConstructor
@Entity
public class Empresa {

    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE, generator = "empresa_sequence")
    @SequenceGenerator(name = "empresa_sequence", sequenceName = "empresa_sequence", allocationSize = 1)
    private Long id;
    private Long codigo;
    private String nome;
    private String cidade;
    private String pais;
    private String adminNome;
    private String adminEmail;

    public static Empresa toEntity(CadastrarEmpresaCommand empresaDto){
        Empresa empresa = new Empresa();
        empresa.setCodigo(empresaDto.getCodigo());
        empresa.setNome(empresaDto.getNome());
        empresa.setCidade(empresaDto.getCidade());
        empresa.setPais(empresaDto.getPais());
        empresa.setAdminNome(empresaDto.getAdminNome());
        empresa.setAdminEmail(empresaDto.getAdminEmail());
        return empresa;
    }


    public static Empresa toEntity(CarregarEmpresaUC empresaDto){
        Empresa empresa = new Empresa();
        empresa.getCodigo();
        empresa.getNome();
        empresa.getCidade();
        empresa.getPais();
        empresa.getAdminNome();
        empresa.getAdminEmail();
        return empresa;
    }
 ```

---

## **Contribuições como Scrum Master**

Durante o desenvolvimento de um sistema web para gestão de tarefas acadêmicas, o cliente — um grupo de alunos e professores — buscava uma solução eficiente para organizar e acompanhar atividades, prazos e responsabilidades de forma colaborativa. O desafio principal era garantir a organização das entregas em um curto espaço de tempo, promovendo integração entre os membros e mantendo a qualidade das entregas, mesmo com diferentes níveis de experiência técnica na equipe.

Como **Scrum Master**, atuei como facilitador do processo de desenvolvimento ágil, com foco em garantir que a equipe seguisse os princípios do **Scrum** de forma disciplinada e produtiva. Minhas principais contribuições envolveram:

* **Planejamento e organização das sprints**, definindo claramente os objetivos de cada ciclo de entrega e promovendo reuniões de planejamento e review com o time.
* **Documentação das tarefas no ClickUp**, o que proporcionou total visibilidade para todos os membros da equipe e permitiu que as atividades fossem monitoradas e atualizadas com clareza.
* **Criação e análise de burndown charts**, que ajudaram a identificar gargalos e ajustar o ritmo de trabalho conforme necessário.
* **Mediação de conflitos e facilitação da comunicação entre membros da equipe**, promovendo um ambiente de cooperação e responsabilidade mútua.
* **Aplicação de cerimônias ágeis** (daily meetings, sprint planning e retrospectivas), aumentando a transparência e a capacidade de adaptação diante de mudanças de escopo.

Essas atividades exigiram o uso efetivo de **hard skills**, como o domínio de ferramentas de gestão ágil, conhecimento de **metodologias ágeis (Scrum)**, e capacidade técnica para dialogar com desenvolvedores sobre **APIs REST**, **HTML/CSS**, e **Vue.js**. Paralelamente, foi essencial o uso de **soft skills**, especialmente **comunicação**, **trabalho em equipe**, **resolução de problemas** e **responsabilidade** para conduzir a equipe de forma colaborativa, focada em resultados.

---

## **Hard Skills**

| Tecnologia/Metodologia | Classificação |
| ---------------------- | ------------- |
| **SQL**                | ★★★★★★☆☆☆☆☆   |
| **MySQL**              | ★★★★☆☆☆☆☆☆    |
| **HTML/CSS**           | ★★★★★★★☆☆☆    |
| **Vue**                | ★★★★★★★☆☆☆    |
| **REST**               | ★★★★★★★☆☆☆    |
| **Scrum**              | ★★★★★★★☆☆☆    |
| **UX/UI Design**       | ★★★★★☆☆☆☆☆    |

### Justificativa

| Tecnologia/Metodologia | Justificativa                                                                                             |
| ---------------------- | --------------------------------------------------------------------------------------------------------- |
| **SQL/MySQL**          | Conhecimento funcional na criação de tabelas e execução de queries simples para apoio ao desenvolvimento. |
| **HTML/CSS**           | Desenvolvimento de layouts para interfaces do sistema com foco em responsividade e usabilidade.           |
| **Vue.js**             | Criação e gerenciamento de componentes dinâmicos e reativos da interface do sistema.                      |
| **REST**               | Apoio na implementação e integração de endpoints RESTful no projeto.                                      |
| **Scrum**              | Atuação direta como facilitador no uso da metodologia, aplicando práticas de planejamento e entrega ágil. |
| **UX/UI Design**       | Criação de wireframes e ajustes de interface baseados no feedback dos usuários finais.                    |

---

## **Soft Skills**

| Habilidade                 | Classificação |
| -------------------------- | ------------- |
| **Comunicação**            | ★★★★★★☆☆☆☆☆   |
| **Trabalho em Equipe**     | ★★★★☆☆☆☆☆☆    |
| **Resolução de Problemas** | ★★★★★★★☆☆☆    |
| **Responsabilidade**       | ★★★★★★☆☆☆☆☆   |

### Justificativa

| Habilidade                 | Justificativa                                                                                              |
| -------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Comunicação**            | Facilitou a compreensão entre membros técnicos e não técnicos, essencial para manter todos alinhados.      |
| **Trabalho em Equipe**     | Participação ativa em decisões do grupo, ajudando na integração entre membros com diferentes experiências. |
| **Resolução de Problemas** | Condução de decisões rápidas durante imprevistos nas sprints, como replanejamento de tarefas prioritárias. |
| **Responsabilidade**       | Garantia de que prazos e entregas fossem cumpridos, mantendo o comprometimento com a qualidade.            |

---




</details>



### 2024 - Segundo Semestre 
- [Link para o README do Projeto 5º Semestre](https://github.com/api-5-sem/api-documentation)



<details>
<summary><b> 2024-2 </b></summary>


# 📊 Projeto de Dashboard Interativo para Análise de Dados de Recrutamento e Seleção - **Pro4tech**

## 🏢 Empresa Parceira: Pro4tech

A **Pro4tech** é uma empresa especializada em **Transformação Digital**, atuando com tecnologias emergentes como **Inteligência Artificial, Análise de Dados, Internet das Coisas (IoT)** e **Computação em Nuvem**. Seu foco é impulsionar empresas por meio da criação de **soluções tecnológicas personalizadas**, aumentando a eficiência e a competitividade dos negócios.

---

## ❗ Descrição do Problema Proposto

A **Pro4tech** identificou a necessidade de um sistema que otimizasse o processo de **recrutamento e seleção**, oferecendo uma solução para:

* Centralizar e acompanhar dados do processo seletivo;
* Avaliar o desempenho de candidatos em cada etapa;
* Analisar o perfil dos candidatos com base na aderência às vagas;
* Fornecer painéis personalizados para tomada de decisões estratégicas;
* Gerenciar diferentes níveis de acesso à informação com segurança.

---

## 💡 Solução Desenvolvida

Foi desenvolvido um **Dashboard Interativo e Modular** com as seguintes funcionalidades principais:

* 📊 **Personalização de Gráficos:**
  Interface intuitiva com filtros dinâmicos e seleção do tipo de gráfico (barra, linha, pizza, etc.), permitindo ao usuário analisar dados de forma personalizada.

* 🔒 **Sistema de Permissões:**
  Controle de acessos baseado em perfis de usuário, assegurando que cada colaborador visualize apenas as informações relevantes ao seu papel.

* 📤 **Exportação de Dados:**
  Possibilidade de exportar gráficos e relatórios em diversos formatos (PDF, CSV, PNG), diretamente da interface do dashboard.

* ⚙️ **Backend Estruturado com API REST:**
  Conjunto de endpoints para criação, leitura, atualização e exclusão (CRUD) dos dados utilizados pelos dashboards, incluindo autenticação segura com JWT.

---

## GitHub do projeto

- [Repositório no GitHub](https://github.com/api-5-sem/api-documentation)

---

## 🛠 Tecnologias Utilizadas

### Backend
- **Java**: Linguagem utilizada no backend, amplamente usada em aplicações web e mobile. Escolhida pela robustez e por ser ensinada na FATEC.
- **Spring Boot**: Framework utilizado para:
  - Configuração e estruturação do projeto.
  - Criação de endpoints.
  - Persistência de dados.
  - Segurança da API.

### Frontend
- **TypeScript**: Substituto ao JavaScript, oferecendo:
  - Maior escalabilidade.
  - Melhor manutenção e depuração do código devido à tipagem estática.
- **Angular**: Framework frontend escolhido por sua simplicidade e facilidade de manutenção, com suporte para componentes reutilizáveis.

### Banco de Dados
- **PostgreSQL**: Banco de dados escolhido pela confiabilidade, performance e facilidade de uso, garantindo a persistência e a integridade dos dados do sistema.

---


## 🙋 **Contribuições Pessoais Detalhadas**


---

### 🔹 Como Desenvolvedor

#### Processamento de excel
Desenvolvi uma função dentro de um componente que é reponsavel por proecessar uma planilha excel de dados e assim enviar esses dados para api que processara os dados do excel, seguindo os passos abaixo:

1. **Criação de botão para enviar arquivo**

   Um tag html foi usada para criar um input do tipo select file onde posso selecionar um arquivo e processalo

```
   <div class="d-flex ms-auto align-items-center">
      <button class="btn btn-light" style="border-radius: 5%;" (click)="triggerFileInput()" aria-label="Importar dados">
        <i class="now-ui-icons files_single-copy-04"></i> Importar
      </button>

      <input type="file" #fileInput style="display: none;" (change)="importDadosProvisionados($event)"
        accept=".xlsx, .xls" />
    </div>

```

Em especifico esse componente visual em Angular utiliza uma div com classes do Bootstrap para alinhar o conteúdo à direita (ms-auto) e centralizar verticalmente os elementos com d-flex e align-items-center. Dentro dessa div, tambem há um botão estilizado com btn btn-light e bordas arredondadas (border-radius: 5%), contendo um ícone da biblioteca Now UI Icons e o texto "Importar". Quando o botão é clicado, ele executa a função triggerFileInput(), que ira  acionar a abertura de um campo de upload de arquivo. Esse campo de upload está logo abaixo, mas está oculto com style="display: none;". É um input do tipo file com a diretiva Angular #fileInput, permitindo que ele seja referenciado no código TypeScrip



2. **Captura do evento click e envio do arquivo**

   Usando uma diretiva que é responsavel por exibir ele primeiro na pagina e é atualizado seu estado quando sofre uma consulta, para isso foi declarado o viewchild

```
      @ViewChild('fileInput') fileInput!: ElementRef;
```

e uma função para capturar esse evento

```
  triggerFileInput() {
    this.fileInput.nativeElement.click();
  }
```



3. **Criação da função**: 
   Definição de um variavel para capturar o arquivo que esta sendo enviado e enviando para a api.


 ```

  importDadosProvisionados(event: any) {
    const file: File = event.target.files[0];

    if (file) {
      this.isLoading = true;

      const formData: FormData = new FormData();
      formData.append('file', file, file.name);

      const headers = new HttpHeaders()
        .set('Authorization', ` ${this.tokenAuth}`)
        .set('enctype', 'multipart/form-data');
  
      this.httpService.post("/api/importacao", formData, { headers })
        .subscribe(
          response => {
            console.log('Arquivo enviado com sucesso', response);
            this.isLoading = false;
          },
          error => {
            console.error('Erro ao enviar arquivo', error);
            this.isLoading = false;
          }
        );
    } else {
      console.log("Nenhum arquivo selecionado.");
    }
  }
```

A função importDadosProvisionados(event: any) é responsável por realizar a importação de um arquivo Excel enviado pelo usuário através de um campo de upload. Quando é selecionado um arquivo, o evento é capturado e o primeiro arquivo da lista é extraído. Em seguida, é criado um objeto FormData, que é usado para enviar dados de formulário contendo arquivos. O arquivo selecionado é adicionado ao FormData com a chave 'file'.

Depois disso, são definidos os cabeçalhos da requisição HTTP, incluindo um cabeçalho de autorização com um token (this.tokenAuth) e o tipo de codificação como multipart/form-data, que é o apropriado para envio de arquivos. O ultimo passo da função  é  fazer uma requisição POST para a URL da nossa api na rota /api/importacao, enviando o FormData com o arquivo e os cabeçalhos configurados. A resposta da requisição é tratada com subscribe: se o envio for bem-sucedido, uma mensagem de sucesso é exibida no console e o carregamento é encerrado; se ocorrer algum erro, uma mensagem de erro é exibida e o carregamento também é encerrado. Caso nenhum arquivo seja selecionado, a função apenas exibe uma mensagem informando que nenhum arquivo foi escolhido.

Detalhes

![image](https://github.com/user-attachments/assets/8089e108-87f6-4492-a72d-b20e7412a223)



4. **Definição de um load**: 
   Definição de um load para que indique o usuario que sua requisição esteja sendo processada.


 ```
.loading {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(255, 255, 255, 0.8);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  color: red;
  z-index: 9999;
}

.spinner {
  width: 40px;
  height: 40px;
  border: 4px solid rgba(0, 0, 0, 0.1);
  border-top: 4px solid red;
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}
```

Detalhes

![image](https://github.com/user-attachments/assets/c00ce3f9-41fe-4343-ac26-fcbe5688f088)


5. **Testes unitario realizado na função**

 Primeiro testado o envio de requisção que ocorre no endpoint da função.Utilizando o mockfile para simular um dado a ser enviado e a função spyOn para que possa ser simulado da chamada da função real e o mesmo comportamento.

 ```
 it('deve enviar o arquivo corretamente via HTTP', () => {
    const mockFile = new File(['mock content'], 'mockFile.txt', { type: 'text/plain' });
    const mockEvent = { target: { files: [mockFile] } };

    component.importDadosProvisionados(mockEvent);

    const req = httpMock.expectOne('/api/importacao');
    expect(req.request.method).toBe('POST');

    req.flush({ success: true });

    expect(component.isLoading).toBeFalse();
  });
 ```
Basicamente a função spyOn é o principal responsavel pelo meu teste nele eu consigo monitorar métodos durante o teste, que pode ser usado para verificar chamadas, interceptar execuções ou simular retornos.


#### Processamento de dados com filtro para os mesmo que reflitam diretamente os dashboard
Desenvolvido um modal e nesse modal eu posso indicar o tipo de dado que quero que seja exibido no meu dashboard:

 ```
<div class="custom-modal">
  <div class="modal-header">
    <h4 class="modal-title">Gerenciamento de Dashboard</h4>
    <button type="button" class="btn-close" aria-label="Close" (click)="close()"></button>
  </div>

  <div class="modal-body">
    <div class="card">
      <div class="card-body">
        <label for="fatoSelect" class="form-label">Descricao:</label>
        <input [formControl]="form.controls.description" class="form-control mb-3">

        <label for="fatoSelect" class="form-label">Escolha o eixo x:</label>
        <select id="fatoSelect" class="form-control mb-3" [formControl]="form.controls.eixoX.get('nome')">
          <option value="" disabled>Selecione um fato</option>
          <option *ngFor="let fato of fatos" [value]="fato.nome">{{fato.alias}}</option>
        </select>

        <label for="dimensaoSelect" class="form-label mt-3">Escolha um valor para o eixo x:</label>
        <select id="dimensaoSelect" class="form-control mb-3" [formControl]="form.controls.eixoX.get('campo')">
          <option value="" disabled>Selecione um campo</option>
          <option *ngFor="let campo of fatosCampos" [value]="campo">{{ formatarString(campo) }}
          </option>
        </select>

        <label for="campoSelect" *ngIf="tipo != 'card'" class="form-label mt-3">Escolha o eixo y :</label>
        <select id="campoSelect" class="form-control mb-3" *ngIf="tipo != 'card'"
          [formControl]="form.controls.eixoY.get('nome')">
          <option value="" disabled>Selecione um campo</option>
          <option *ngFor="let d of dimensao" [value]="d.nome">{{ d.alias }}</option>
        </select>


        <label for="campoDimensaoSelect" *ngIf="tipo != 'card'" class="form-label mt-3">Escolha um valor para o eixo
          y:</label>
        <select id="campoDimensaoSelect" *ngIf="tipo != 'card'" class="form-control mb-3"
          [formControl]="form.controls.eixoY.get('campo')">
          <option value="" disabled>Selecione um campo</option>
          <option *ngFor="let campo of dimensaoCampos" [value]="campo">{{ formatarString(campo) }}</option>
        </select>


        <label for="campoDimensaoSelect" class="form-label mt-3">Escolha o filtro :</label>
        <select id="campoDimensaoSelect" class="form-control mb-3"
          [formControl]="form.controls.filtros.get('0').get('nome')">
          <option value="" disabled>Selecione um campo</option>

          <option *ngFor="let d of dimensao" [value]="d.nome">{{ d.alias }}</option>
        </select>


        <label for="campoDimensaoSelect" class="form-label mt-3">Escolha um campo/valor para filtrar:</label>
        <select id="campoDimensaoSelect" class="form-control mb-3"
          [formControl]="form.controls.filtros.get('0').get('campo')">
          <option value="" disabled>Selecione um campo</option>
          <option *ngFor="let campo of filtroCampos" [value]="campo">{{ formatarString(campo) }}</option>
        </select>

        <label for="campoDimensaoSelect" class="form-label mt-3">Escolha um comparador:</label>
        <select id="campoDimensaoSelect" class="form-control mb-3"
          [formControl]="form.controls.filtros.get('0').get('comparador')">
          <option value="" disabled>Selecione um campo</option>
          <option value="=">=</option>
          <option value=">=">>=</option>
          <option value="<=">
            <= </option>
          <option value=">">></option>
          <option value="<">
            < </option>
        </select>

        <label for="campoDimensaoSelect" class="form-label mt-3">Escolha um valor do filtro:</label>
        <input id="campoDimensaoSelect" class="form-control mb-3"
          [formControl]="form.controls.filtros.get('0').get('valor')" />

      </div>
    </div>


    <div class="modal-footer">
      <button type="button" class="btn btn-secondary" (click)="close()">Fechar</button>
      <button type="button" class="btn btn-primary" (click)="configure()">Configurar</button>
    </div>
  </div>
</div>
 ```


criação da lógica de como meu componente deve se comporta ao mudar um item no meu combos.Sendos os fatos e dimensões valores preenchidos com base na minha api sempre que uma ação de clique no meu combo for disparada


```
  ngOnInit(): void {
    this.createForm();
    this.getFatos();

    this.form.controls.eixoX.get('nome').valueChanges.subscribe(val => {
      const fato = this.fatos.filter(x => x.nome == val)[0]
      this.fatosCampos = fato.campos[0].split(',')
      this.onFatoChange(val);
    })

    this.form.controls.eixoY.get('nome').valueChanges.subscribe(val => {
      const dimensao = this.dimensao.filter(x => x.nome == val)[0]
      this.dimensaoCampos = dimensao.campos[0].split(',')
    })

    this.form.controls.filtros.get('0').get('nome').valueChanges.subscribe(val => {
      const filtros = this.dimensao.filter(x => x.nome == val)[0]
      this.filtroCampos = filtros.campos[0].split(',')
    })
  }



  createForm() {
    this.form = new FormGroup({
      description: new FormControl('', []),
      eixoX: new FormGroup({
        nome: new FormControl('', []),
        campo: new FormControl('', []),
      }),
      eixoY: new FormGroup({
        nome: new FormControl('', []),
        campo: new FormControl('', []),
      }),
      filtros: new FormArray([new FormGroup({
        nome: new FormControl('', []),
        campo: new FormControl('', []),
        comparador: new FormControl('', []),
        valor: new FormControl('', [])
      })])
    })
  }

  getFatos(): void {
 
    const headers = new HttpHeaders().set('Authorization', `${this.tokenAuth}`);

    this.httpService.get("http://localhost:8080/filtros/fatos", { headers })
      .subscribe({
        next: (responses: any[]) => {
          this.fatos = responses
        }
      });
  }

  onFatoChange(value: string): void {
    
    const headers = new HttpHeaders().set('Authorization', `${this.tokenAuth}`);

    this.httpService.get(`http://localhost:8080/filtros/dimensoes?fato=${value}`, { headers })
      .subscribe({
        next: (response: any[]) => {
          this.dimensao = response;
        }
      });
  }



  configure(): void {
    const form = this.form.value;
    if (!this.form.controls.filtros.get('0').get('nome').value) {
      form.filtros = [];
    }
    sessionStorage.setItem(this.tipo + this.idXGrafico, JSON.stringify(form))
  }

}
```

A função `ngOnInit()` inicializa o formulário e define assinaturas para reagir às mudanças nos campos do formulário, atualizando campos relacionados conforme a seleção do usuário. A função `createForm()` cria a estrutura do formulário reativo com grupos e arrays de controles para captar os dados necessários. A função `getFatos()` faz uma requisição HTTP autenticada para buscar os dados de fatos no backend e armazená-los para uso posterior. Já a função `onFatoChange()` é acionada quando o fato muda, buscando as dimensões correspondentes via HTTP e atualizando os dados disponíveis no formulário.

Detalhes

![image](https://github.com/user-attachments/assets/7d195df6-ff96-4cf3-9dfd-23a33e2da7c4)



2. Processamento dos dados no dashboard com base no meu conteudo que foi filtrado e gravado no meu session storage meu componente dashboard recupera seus dados ao ser inicializado no session storage, como pode se ver na função abaixo


   
```
  createCardRequest(idx: number): DashboardRequest {
    if (idx == 1) {
      const cardOne = JSON.parse(sessionStorage.getItem("card1")) as DashboardRequest;

      if (cardOne) {
        return cardOne
      }
      else {
        return {
          'description': 'Vagas em aberto',
          'eixoX': {
            'nome': 'fato_vaga',
            'campo': 'nr_posicoes_abertas'
          },
          'filtros': []
        }
      }
    }

    if (idx == 2) {
      const cardTwo = JSON.parse(sessionStorage.getItem("card2")) as DashboardRequest;

      if (cardTwo) {
        return cardTwo
      }
      else {
        const now = new Date();
        now.setDate(now.getDate() - 7)

        return {
          'description': 'Entrevistas marcadas',
          'eixoX': {
            'nome': 'fato_entrevista',
            'campo': 'nr_entrevistas'
          },
          'filtros': [
            {
              'nome': 'dim_entrevista',
              'campo': 'dt_entrevista',
              'valor': now.toISOString().split('T')[0],
              'comparador': '>='
            }
          ]
        }
      }
    }

    const cardThree = JSON.parse(sessionStorage.getItem("card3")) as DashboardRequest;
    if (cardThree) {
      return cardThree
    }

    return {
      'description': 'Feedbacks Totais',
      'eixoX': {
        'nome': 'fato_entrevista',
        'campo': 'nr_entrevistas'
      },
      'filtros': []
    }
  }

  createGraphicRequest(idx: number): DashboardRequest {

    if (idx == 1) {
      const grafico1 = JSON.parse(sessionStorage.getItem("grafico1")) as DashboardRequest;
      if (grafico1) {
        return grafico1;
      }
      else {
        return {
          'description': 'Tempo medio do processo',
          "eixoX": {
            "nome": "fato_vaga",
            "campo": "tempo_medio_processo"
          },
          "eixoY": {
            "nome": "dim_vaga",
            "campo": "titulo"
          },
          "filtros": [
            {
              "nome": "dim_periodo",
              "campo": "dt_abertura",
              "comparador": ">=",
              "valor": "2000-09-22"
            }
          ]
        }
      }
    }
    if (idx == 2) {
      const grafico2 = JSON.parse(sessionStorage.getItem("grafico2")) as DashboardRequest;
      if (grafico2) {
        return grafico2;
      }
      else {
        return {
          'description': 'Numero de processos abertos nos ultimos 12 meses ',
          "eixoX": {
            "nome": "fato_vaga",
            "campo": "nr_posicoes_abertas"
          },
          "eixoY": {
            "nome": "dim_vaga",
            "campo": "titulo"
          },
          "filtros": [
            {
              "nome": "dim_periodo",
              "campo": "dt_abertura",
              "comparador": ">=",
              "valor": "2023-09-22"
            }
          ]
        }
      }
    }

    const grafico2 = JSON.parse(sessionStorage.getItem("grafico3")) as DashboardRequest;
    if (grafico2) {
      return grafico2;
    }

    return {
      'description': 'Feedbacks recebidos',
      eixoX: {
        nome: "fato_entrevista",
        campo: "nr_entrevistas"
      },
      eixoY: {
        nome: "dim_feedback",
        campo: "descricao"
      },
      "filtros": [
        {

          "nome": "dim_entrevista",
          "campo": "dt_entrevista",
          "comparador": ">=",
          "valor": "2023-09-22"
        }
      ]
    }
  }
```

#### Tela de login para adentrar no sistema com autenticação via token
Desenvolvido uma tela de login para poder adentrar no sistema:

```
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Login Page</title>
</head>
<body>
  <div class="container">
    <!-- Seção Esquerda -->
    <div class="left-section">
      <div class="logo-container">
        <img src="./assets/img/logo-p4t-navbar-branco.png" alt="Logo" class="logo">
        <h2 class="welcome-title">Bem-vindo ao Nosso Portal</h2>
        <p class="welcome-text">Acesse sua conta para explorar todas as funcionalidades</p>
      </div>
    </div>

    <!-- Seção Direita (Login) -->
    <div class="right-section">
      <div class="login-card">
        <form [formGroup]="loginForm"> 
          <div class="form-group">
            <label for="login" class="form-label">Login</label>
            <input formControlName="login" type="email" id="login"  placeholder="Digite seu login" required />
          </div>
          <div class="form-group">
            <label for="password" class="form-label">Senha</label>
            <input formControlName="password" type="password" id="password"  placeholder="Digite sua senha" required />
          </div>
          <button type="button" class="btn-primary" (click)="onLoginClick()">Entrar</button>
        </form>
        <div class="text-center mt-3">
        </div>
      </div>
    </div>
  </div>
</body>
</html>
```

Uma estilização para esse componente de login

```
.card {
    display: flex;
    flex-direction: column; 
    justify-content: center; 
    align-items: center;
    margin: 0 auto; 
    width: 100%; 
    max-width: 400px; 
    padding: 2rem; 
    margin-top: 100px; 
    margin-bottom: 85px; 
    
    border-radius: 12px; 
    border: 2px solid #ffa228; 
    background-color: #f5f5f5; 
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); 
}

input {
    width: 100%;
    padding: 1.3rem; 
    margin-bottom: 1rem;
    border: 2px solid #ffa228; 
    font-size: 1.1rem; 
}

button {
    background-color: #ffa228; 
    color: white;
    padding: 0.75rem;
    border: none;
    border-radius: 6px;
    font-size: 1rem;
    cursor: pointer;
    width: 100%;
}

button:hover {
    background-color: #0056b3;
}

  @media (max-width: 768px) {
    .container {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }
    
    .image-container {
      margin-bottom: 20px;
    }
    
    .image-container img {
      margin-right: 0; 
    }
  }/* Reset básico */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  body {
    font-family: Arial, sans-serif;
    background-color: #FF9800;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    margin: 0;
  }
  
  /* Container principal */
  .container {
    display: flex;
    width: 100%;
    max-width: 1200px;
    height: 80vh;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  }
  
  .left-section {
    flex: 1;
    background-color: #FF9800;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 40px;
    color: #fff;
    text-align: center;
  }
  
  .right-section {
    flex: 1;
    background-color: #f7f7f7;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 40px;
  }
  
  /* Logo e texto de boas-vindas */
  .logo-container {
    max-width: 300px;
  }
  
  .logo {
    max-width: 150px;
    margin-bottom: 20px;
  }
  
  .welcome-title {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 10px;
  }
  
  .welcome-text {
    font-size: 16px;
  }
  
  /* Card de login */
  .login-card {
    width: 100%;
    max-width: 400px;
    background-color: #fff;
    padding: 30px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  
  .form-group {
    margin-bottom: 20px;
  }
  
  .form-label {
    display: block;
    margin-bottom: 8px;
    font-weight: bold;
    color: #333;
  }
  
  .form-control {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  
  .btn-primary {
    width: 100%;
    padding: 12px;
    background-color: orange ;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    transition: background-color 0.3s ease;
  }
  
  .btn-primary:hover {
    background-color: #ec463a;
  }
  
  .forgot-password-link {
    color: #007bff;
    font-size: 14px;
    text-decoration: none;
  }
  
  .forgot-password-link:hover {
    text-decoration: underline;
  }
  
  /* Responsividade para dispositivos móveis */
  @media (max-width: 768px) {
    .container {
      flex-direction: column;
      height: auto;
      margin: 20px;
    }
  
    .left-section,
    .right-section {
      width: 100%;
      padding: 20px;
    }
  
    .logo {
      max-width: 120px;
    }
  
    .welcome-title {
      font-size: 20px;
    }
  
    .welcome-text {
      font-size: 14px;
    }
  
    .login-card {
      width: 100%;
      padding: 25px;
    }
  
    .btn-primary {
      font-size: 14px;
      padding: 10px;
    }
  }
```

e a logica do meu componete de login que sera capturar os dados digitados no meu formulario processar o que foi digitado e enviado para logar no sistema

```
  onLoginClick(): void {
    if (this.loginForm.valid == false)  {
      const loginData = this.loginForm.value;
      
      this.http.post<{ token: string; permissaoGrupoProjection: string;}>
            (`${this.apiUrl}/login`, loginData)

      .subscribe({
        next: (response) => {
          localStorage.setItem('authToken', response.token);
          localStorage.setItem('permissions',JSON.stringify(response.permissaoGrupoProjection));
            this.navigate.navigate(['/dashboard']) ;
        },
        error: (error) => {
          console.error('Erro no login:', error);
        }
      });
    } else {
      console.log('Formulário de login inválido');
    }
  }
```

Detalhes

![image](https://github.com/user-attachments/assets/9c89b811-99d6-44f4-a395-e2caddb1de2f)


#### Tela para gerar relatorios
Desenvolvido uma funcionalidade na tela de gerar relatorios, que permite o usuario escolher entre o tipo de relatorio se deseja pdf ou excel:


```
gerarRelatorio() {
     const data = this.request;
   
     const token = 'Bearer ' +localStorage.getItem("authToken");
     const command = data;
   
     this.http.post('http://localhost:8080/relatorio', command, {
       responseType: 'blob',
       observe: 'response',
       headers: {
         Authorization: token 
       }
     }).subscribe(
       (response) => {
         console.log(response)
         const blob = new Blob([response.body], { type: 'application/vnd.ms-excel' });
         const url = window.URL.createObjectURL(blob);
   
         const a = document.createElement('a');
         a.href = url;
         a.download = 'Relatorio.xlsx';
         a.click();
         window.URL.revokeObjectURL(url);
       },
       (error) => {
         console.error('Erro ao gerar o relatório:', error);
       }
     );
   }

```

que basicamente recebe os dados da api ja convertendo no formato excel e realiza o dowload do mesmo


Detalhes

![image](https://github.com/user-attachments/assets/df88863a-317a-4ca4-b197-cfc6ff398b32)



### 🔹 Como DEVOPS

Autei lidando na construção da nossa esteira de automação, o nosso continuos integration. Que é composto por 3 frentes o build, teste, deploy e notificação do sucesso desse processo. Nesse ci foi integrado como nosso processo de desenvolvimento que consistia em adotar um padrao de branch, e validando cada integração de novas funcionalidades até as que as mesma chegassem no ramo principal. Após essa validação que é execultada com teste unitarios, teste de carga e versionamento do nosso banco de dados. Caso nenhuma validação falhe e como mencionado as integrações cheguem ao ramo principal é feito o  build e subido esse conteudo para um container do acr da azure onde realizamos nosso deploy


Action para nosso deploy

```
name: CI/CD Pipeline

on:
  push:
  pull_request:
    branches:
      - main
      - develop
  schedule:
    - cron: '0 18 * * *'

jobs:
  
  build:
    name: Build and Test
    runs-on: ubuntu-latest

    steps:
      # Checkout do código
      - uses: actions/checkout@v3

      # Configuração do Node.js
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '20.x'

      # Instalar dependências
      - name: Install dependencies
        run: npm ci
        working-directory: ./api

      # Instalar Angular CLI
      - name: Install Angular CLI
        run: npm install -g @angular/cli@13
        working-directory: ./api

      # Executar testes unitários (somente na branch develop)
      - name: Run unit tests
        if: github.ref == 'refs/heads/develop'
        run: ng test --watch=false --browsers=ChromeHeadless
        working-directory: ./api

  build-and-push-acr:
    name: Build and Push to Azure Container Registry
    runs-on: ubuntu-latest
    if: github.event_name == 'pull_request' && github.base_ref == 'main' # Apenas PR para main

    steps:
    - uses: actions/checkout@master
    
    - uses: Azure/docker-login@v1
      with:
        login-server: angularapp.azurecr.io
        username: ${{ secrets.ACR_USERNAME }}
        password: ${{ secrets.ACR_PASSWORD }}
    
    - run: |
        docker build . -t angularapp.azurecr.io/frontend:${{ github.sha }}
        docker push angularapp.azurecr.io/frontend:${{ github.sha }}
      
    # Set the target AKS cluster.
    - uses: Azure/aks-set-context@v1
      with:
        creds: '${{ secrets.AZURE_CREDENTIALS }}'
        cluster-name: pixelCluster
        resource-group: gr-pixel-containers
      
    - name: Update deployment image
      run: |
        sed -i 's|<IMAGE_PLACEHOLDER>|angularapp.azurecr.io/frontend:${{ github.sha }}|' k8s/deployment.yaml
    - uses: Azure/k8s-deploy@v1
      with:
        manifests: |
          k8s/deployment.yaml
          k8s/service.yaml
        images: |
          angularapp.azurecr.io/frontend:${{ github.sha }}
        imagepullsecrets: |
          k8s-secret-front
        namespace: ingress-basic

  notifyTelegramSuccess:
    runs-on: ubuntu-latest
    needs: [build-and-push-acr, build]
    if: success()
    steps:
      - name: Send Telegram Notification (Success)
        uses: appleboy/telegram-action@v1.0.0
        with:
          to: -4512389085
          token: 7965658930:AAH9K3d8Y2HD73FuMZ7Ys9RSjYfmfErd2zw
          message: |
            ✅ CI/CD Pipeline Status:
            - Evento: ${{ github.event_name }}
            - Branch: ${{ github.ref_name }}
            - Status: Concluído com sucesso!

  notifyTelegramFailure:
    runs-on: ubuntu-latest
    needs: [build-and-push-acr, build]
    if: failure()
    steps:
      - name: Send Telegram Notification (Failure)
        uses: appleboy/telegram-action@v1.0.0
        with:
          to: -4512389085
          token: 7965658930:AAH9K3d8Y2HD73FuMZ7Ys9RSjYfmfErd2zw
          message: |
            ❌ CI/CD Pipeline Failed:
            - Evento: ${{ github.event_name }}
            - Branch: ${{ github.ref_name }}
            - Status: Falha no pipeline. Verifique os logs para mais detalhes!
```



Na primeira etapa como ja comentado,é chamada de build, o workflow instala as dependências do projeto localizado no diretório ./api, configura o ambiente Node.js e instala o Angular CLI. Caso a branch seja develop, ele também executa testes unitários com o comando ng test, garantindo que o código esteja funcionando corretamente. Em seguida, na etapa build-and-push-acr, que roda apenas quando há um pull request direcionado à branch main, o código é empacotado em uma imagem Docker e enviado ao Azure Container Registry (ACR). Após isso, o pipeline conecta-se ao cluster Kubernetes no Azure (AKS) e atualiza a aplicação com a nova imagem, utilizando os arquivos de manifesto deployment.yaml e service.yam

---


## **Hard Skills**

| Tecnologia/Metodologia | Classificação |
| ---------------------- | ------------- |
| **HTML/CSS**           | ★★★★☆☆☆☆☆☆    |
| **Angular**            | ★★★★★☆☆☆☆☆    |
| **GitHub/Actions**     | ★★★★★☆☆☆☆☆    |
| **TypeScript**         | ★★★★★★★★★★    |
| **Scrum**              | ★★★★★★★★★★    |
| **UX/UI Design**       | ★★★★★★★★★★    |

### **Justificativas – Hard Skills**

| Tecnologia/Metodologia | Justificativa                                                                                                                                         |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **HTML/CSS**           | Conhecimento funcional para estruturar páginas e aplicar estilos básicos, suficiente para prototipagem rápida e suporte ao front-end.                 |
| **Angular**            | Experiência prática na construção de componentes reutilizáveis, integração com serviços e utilização de rotas e diretivas da framework.               |
| **GitHub/Actions**     | Capacidade de utilizar versionamento de código com Git e configurar automações com GitHub Actions para integração e entrega contínua (CI/CD).         |
| **TypeScript**         | Domínio avançado na criação de aplicações robustas com tipagem estática, interfaces e princípios de orientação a objetos.                             |
| **Scrum**              | Atuação efetiva como Scrum Master, facilitando cerimônias ágeis e aplicando boas práticas para promover a entrega contínua e o alinhamento da equipe. |
| **UX/UI Design**       | Forte habilidade em desenvolver interfaces centradas no usuário, aplicando princípios de usabilidade, acessibilidade e design responsivo.             |

---

## **Soft Skills**

| Habilidade                 | Classificação |
| -------------------------- | ------------- |
| **Comunicação**            | ★★★★★★★☆☆☆☆   |
| **Trabalho em Equipe**     | ★★★★★★★★☆☆    |
| **Resolução de Problemas** | ★★★★★★★☆☆☆    |
| **Responsabilidade**       | ★★★★★★★☆☆☆    |

### **Justificativas – Soft Skills**

| Habilidade                 | Justificativa                                                                                                                                                                |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Comunicação**            | Capacidade sólida de articular ideias com clareza em diferentes canais (oral e escrito), facilitando a troca de informações entre áreas técnicas e não técnicas.             |
| **Trabalho em Equipe**     | Experiência em ambientes colaborativos, atuando com empatia e proatividade na resolução de conflitos e na divisão de responsabilidades durante o projeto.                    |
| **Resolução de Problemas** | Habilidade em diagnosticar causas de erros técnicos, propor soluções rápidas e eficientes, com foco em otimizar a experiência do usuário e manter a estabilidade do sistema. |
| **Responsabilidade**       | Comprometimento constante com prazos e metas do projeto, demonstrando organização, foco em resultados e entrega de qualidade.                                                |

---


  
</details>

### 2025 - Primeiro Semestre 
- [Link para o README do Projeto 6º Semestre](https://github.com/api-6-pixel/api-doc)


<details>
  <summary><b> 2025-1 </b></summary>

  #  📊 Projeto de Indicadores Inteligentes para Análise de Dados - **Kersys**

  ## 🏢 Empresa Parceira: Kersys


A **Kersys** é uma empresa especializada em soluções inteligentes voltadas ao setor agroambiental, com foco na **gestão sustentável de reflorestamentos**. O cliente atua diretamente com produtores, consultores ambientais e órgãos reguladores, oferecendo ferramentas para  monitoramento, planejamento e conformidade ambiental.



## ❗ Descrição do Problema Proposto

A empresa enfrentava desafios no **planejamento estratégico e acompanhamento das áreas reflorestadas**, principalmente no que diz respeito a:

* **Previsão de crescimento das árvores** com base em variáveis ambientais e operacionais;
* **Estimativas de custo** associadas ao processo de reflorestamento;
* **Organização e atualização diária de dados** da plantação por parte dos usuários;
* Necessidade de uma **ferramenta intuitiva, integrada e segura** para tomada de decisão no campo.

---



## 💡 Solução Desenvolvida

Nosso sistema proporcionará um controle eficiente de dados agrícolas, abrangendo informações sobre plantio, espécies cultivadas, condições ambientais e lotes. Com uma interface intuitiva, os usuários poderão acompanhar esses dados em tempo real, garantindo maior organização e precisão no gerenciamento dos lotes.

O principal objetivo é permitir a projeção detalhada do crescimento da colheita mês a mês, facilitando o planejamento estratégico e a tomada de decisões. Além disso, o sistema oferecerá estimativas do custo projetado para o tratamento de cada lote e tipo de solo, auxiliando no controle financeiro e na otimização dos recursos disponíveis

---

## GitHub do projeto

- [Repositório no GitHub](https://github.com/api-5-sem/api-documentation)




## 🙋 **Contribuições Pessoais Detalhadas**

Atuei nas áreas de **desenvolvimento front-end e back-end**, com foco nos seguintes módulos:

---

### 🔐 **1. Módulo de Consentimento de Uso de Dados (LGPD)**

#### 🧩 Modelagem de Dados

A estrutura de banco foi organizada conforme o diagrama:

![modelagem-termo](https://github.com/user-attachments/assets/6afba74e-98a1-47ea-8ebb-daf9572c5b3c)

#### 📦 Entidade: `TermoItemAceite`

```java
package br.gov.sp.cps.api.pixel.core.domain.entity;

import jakarta.persistence.*;
import lombok.*;

@Entity
@Table(name = "tb_cad_termo_item_aceite")
@Getter
@Setter
@NoArgsConstructor
@AllArgsConstructor
public class TermoItemAceite {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long codigo;

    @ManyToOne
    @JoinColumn(name = "termo_aceite_codigo", nullable = false)
    private TermoItemAceiteUsuarioHistorico termoAceiteUsuarioHistorico;

    @ManyToOne
    @JoinColumn(name = "termo_item_codigo", nullable = false)
    private TermoItem termoItem;

    private boolean aceito;
}
```

#### 📦 Entidade: `TermoItemAceiteUsuarioHistorico`

```java
package br.gov.sp.cps.api.pixel.core.domain.entity;

import lombok.*;
import jakarta.persistence.*;
import java.time.LocalDateTime;

@Entity
@Table(name = "tb_cad_termo_item_aceite_usuario_historico")
@Getter
@Setter
@NoArgsConstructor
@AllArgsConstructor
public class TermoItemAceiteUsuarioHistorico {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long codigo;

    @ManyToOne
    @JoinColumn(name = "usuario_codigo", nullable = false)
    private Usuario usuario;

    @ManyToOne
    @JoinColumn(name = "termo_codigo", nullable = false)
    private Termo termo;

    private LocalDateTime dataAceite;
    private LocalDateTime dataAlteracao;
}
```

#### 🖥️ Interface do Usuário

![UI Screenshot](https://github.com/user-attachments/assets/17ef24fb-b06b-444e-ad0c-438d1a61c896)

#### ✅ Funcionalidades

* Registro de versões e histórico dos termos aceitos;
* Interfaces intuitivas para o usuário aceitar os termos;
* Garantia de conformidade com a **Lei Geral de Proteção de Dados (LGPD)**.

---

### 🧾 **2. Tela de Itens do Termo**

* Área administrativa para cadastrar, editar e excluir itens de consentimento;
* Integração com o módulo LGPD, refletindo as alterações em tempo real.

#### 🔗 Função `enviarDados()`

```typescript
enviarDados() {
  const termo = localStorage.getItem("termo");
  if (termo === "recusou" || this.abriu === false || this.enviando) return;

  if (!this.usuarioNome || !this.email || !this.senha || !this.cpf) {
    this.exibirToast("Por favor, preencha todos os campos obrigatórios.", "danger");
    return;
  }

  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  if (!emailRegex.test(this.email)) {
    this.exibirToast("Por favor, insira um e-mail válido.", "warning");
    return;
  }

  const body = {
    nome: this.usuarioNome,
    nomeUsuario: this.usuarioNome,
    email: this.email,
    senha: this.senha,
    documento: this.cpf,
    funcao: "USUARIO"
  };

  this.enviando = true;

  this.http.post("usuarios", body)
    .then((response: any) => {
      const idUsuario = response.id;

      this.exibirToast("Cadastro realizado com sucesso!", "success");

      const termos = localStorage.getItem("termos");
      if (termos) {
        const termosAceitos = JSON.parse(termos);
        const aceitos = termosAceitos.respostas;
        const codigos = termosAceitos.termoItemCodigo;

        const promessas = codigos.map((codigo: number, i: number) => {
          return this.http.post("historico/aceite", {
            aceito: aceitos[i],
            termoItemCodigo: codigo,
            usuarioCodigo: idUsuario
          });
        });

        Promise.all(promessas)
          .then(() => this.exibirToast("Termos aceitos!", "success"))
          .catch(error => console.error("Erro ao aceitar termos:", error));
      }
    })
    .catch(error => console.error("Erro ao cadastrar usuário:", error))
    .finally(() => this.enviando = false);
}
```

#### 📄 Componente HTML

```html
<ion-header>
  <ion-toolbar>
    <ion-title>Termo de Consentimento LGPD</ion-title>
    <ion-buttons slot="end">
      <ion-button color="medium" (click)="concordar()">Fechar</ion-button>
    </ion-buttons>
  </ion-toolbar>
</ion-header>

<ion-content class="ion-padding" appScrollbar>
  <ion-card>
    <ion-card-header>
      <ion-card-title>Uso de Dados Pessoais</ion-card-title>
    </ion-card-header>
    <ion-card-content>
      <p>
        Conforme a LGPD (Lei nº 13.709/2018), precisamos do seu consentimento para tratar seus dados pessoais.
        Leia os itens abaixo e marque os que concorda.
      </p>
    </ion-card-content>
  </ion-card>

  <ion-list *ngIf="itensObrigatorios?.length || itensOpcionais?.length">
    <ion-list-header color="light">
      <ion-label><strong>Consentimentos Obrigatórios</strong></ion-label>
    </ion-list-header>

    <ion-item *ngFor="let item of itensObrigatorios">
      <ion-checkbox slot="start" [(ngModel)]="respostas[item.codigo]"></ion-checkbox>
      <ion-label>{{ item.descricao }} <strong class="text-danger">*</strong></ion-label>
    </ion-item>

    <ion-list-header *ngIf="itensOpcionais?.length" color="light" class="ion-margin-top">
      <ion-label><strong>Consentimentos Opcionais</strong></ion-label>
    </ion-list-header>

    <ion-item *ngFor="let item of itensOpcionais">
      <ion-checkbox slot="start" [(ngModel)]="respostas[item.codigo]"></ion-checkbox>
      <ion-label>{{ item.descricao }}</ion-label>
    </ion-item>
  </ion-list>

  <ion-note color="medium" class="ion-padding">
    Você pode revogar seu consentimento a qualquer momento nas configurações de privacidade ou contato com o suporte.
  </ion-note>
</ion-content>
```

---

### 🧭 **3. Menu de Navegação**

* Menu lateral responsivo com **Ionic Split Pane**;
* Compatível com dispositivos móveis.

#### 🛣️ Rotas

```typescript
import { Routes } from '@angular/router';

export const routes: Routes = [
  { path: '', redirectTo: 'folder/inbox', pathMatch: 'full' },
  { path: 'folder/:id', loadComponent: () => import('./folder/folder.page').then(m => m.FolderPage) },
  { path: 'dashboard', loadComponent: () => import('./dashboard/dashboard.component').then(m => m.DashboardComponent) },
  { path: 'folder/cadastro', loadComponent: () => import('./cadastro/cadastro.component').then(m => m.CadastroComponent) }
];
```

#### 📁 Componente do Menu

```html
<ion-split-pane id="menu" [ngClass]="isOpenMenu ? 'open' : ''" when="xs" contentId="main">
  <ion-menu contentId="main" style="margin-top: 30px;">
    <ion-label class="ion-align-items-center">
      <h1 class="ion-text-center" style="font-size: 30px;">K</h1>
    </ion-label>

    <ion-content>
      <ng-container *ngFor="let menu of menus;">
        <div class="menu-item" [routerLink]="['/' + menu.link]" routerLinkActive="selected">
          <ion-icon [name]="menu.icon"></ion-icon>
          <ion-label [ngClass]="isOpenMenu ? '' : 'close'">{{ menu.caption }}</ion-label>
        </div>
      </ng-container>
    </ion-content>

    <ion-row class="icon-container">
      <ion-icon name="chevron-forward-outline" *ngIf="!isOpenMenu" (click)="openMenu(true)"></ion-icon>
      <ion-icon name="chevron-back-outline" *ngIf="isOpenMenu" (click)="openMenu(false)"></ion-icon>
    </ion-row>
  </ion-menu>

  <div class="ion-page" id="main">
    <ion-content id="menu-content">
      <ion-router-outlet></ion-router-outlet>
    </ion-content>
  </div>
</ion-split-pane>
```
#### 🖥️ Interfaces


![image](https://github.com/user-attachments/assets/3d5ecf68-51f9-426b-884f-964ab0738ae6)





### 📊 **4. Dashboard de Monitoramento**

* Desenvolvimento de uma tela com **gráficos interativos** que exibem:

  * Crescimento estimado da colheita ao longo de 10 meses;
  * Projeção de custos operacionais;
* Utilização de bibliotecas de visualização de dados integradas ao **Angular**.



Desenvolvido o dashboard


```html
<ion-content appScrollbar>
  <ion-grid  class="plantacao-fundo">
    <ion-row class="ion-justify-content-center">
      <ion-col size="12" size-md="5">
        <ion-card>
          <ion-card-header>
            <ion-title class="ion-text-center">
              <ion-icon name="leaf-outline "></ion-icon> CRESCIMENTO DA COLEITA
            </ion-title>
          </ion-card-header>
          <ion-card-content>
            <p-chart type="line" [data]="growthData" style="max-width: 100%; height: 120px;"></p-chart>
          </ion-card-content>
        </ion-card>
      </ion-col>

      <ion-col size="12" size-md="5">
        <ion-card>
          <ion-card-header>
            <ion-title class="ion-text-center">
              <ion-icon name="cash-outline"></ion-icon> PROJEÇÃO FINANCEIRA
            </ion-title>
          </ion-card-header>
          <ion-card-content>
            <p-chart type="bar" [data]="financeData" style="max-width: 100%; height: 120px;"></p-chart>
          </ion-card-content>
        </ion-card>
      </ion-col>
    </ion-row>

    <ion-row class="ion-justify-content-center">
      <ion-col size="12" size-md="5">
        <ion-card>
          <ion-card-header>
            <ion-title class="ion-text-center">
              <ion-icon name="analytics-outline"></ion-icon> GASTOS COM SOLO
            </ion-title>
          </ion-card-header>
          <ion-card-content>
            <p-chart type="pie" [data]="soilData" style="max-width: 100%; height: 120px;"></p-chart>
          </ion-card-content>
        </ion-card>
      </ion-col>
    </ion-row>
  </ion-grid>
</ion-content>


```


#### 🖥️ Interfaces


![image](https://github.com/user-attachments/assets/3b789fca-808e-44c5-b563-6fc41cbeecb8)






---

### 🌱 **5. Tela de Atualização de Plantio**

Interface onde o usuário pode inserir **dados diários da plantação**, como:

* Temperatura ambiente e do solo
* Umidade do ambiente e do solo
* pH do solo
* Índice UV
* Seleção do lote (identificado pelo nome da fazenda)

Os dados são armazenados em bancos de dados **relacional** (`PostgreSQL`) e **não relacional** (`MongoDB`) para permitir cruzamento de informações e análises avançadas.

---


#### 🖼️ **Interface**


<img src="https://github.com/user-attachments/assets/b38d7673-1354-40d8-a3df-7a12b8f56781" alt="Tela de Atualização de Plantio" width="800"/>

---

#### 🧠 **Lógica de Envio de Dados (TypeScript)**

```typescript
async enviarDados() {
  if (
    !this.plantacaoId || this.temperaturaAmbiente === null || this.temperaturaSolo === null ||
    this.umidadeAmbiente === null || this.umidadeSolo === null || this.phSolo === null ||
    this.indiceUV === null
  ) {
    this.exibirToast("Preencha todos os campos obrigatórios!", "danger");
    return;
  }

  const dados = {
    plantacaoId: this.plantacaoId,
    fazendaNome: this.fazendaNome,
    temperaturaAmbiente: this.temperaturaAmbiente,
    temperaturaSolo: this.temperaturaSolo,
    umidadeAmbiente: this.umidadeAmbiente,
    umidadeSolo: this.umidadeSolo,
    phSolo: this.phSolo,
    indiceUV: this.indiceUV,
  };

  this.http.post("atualizacoes", dados).then(() => {
    this.exibirToast("Dados enviados com sucesso!", "success");
    this.router.navigate(['/dashboard']);
  }).catch((error) => {
    const mensagemErro = error?.message || "Erro desconhecido";
    this.exibirToast(`Erro ao enviar os dados! Erro: ${mensagemErro}`, "danger");
  });
}
```

---

#### 🧾 **Formulário HTML (Ionic)**

```html
<ion-content appScrollbar>
  <ion-card>
    <ion-card-header>
      <ion-title class="ion-text-center">
        <ion-icon name="leaf-outline"></ion-icon> FORMULÁRIO DE PLANTAÇÃO
      </ion-title>
    </ion-card-header>

    <ion-card-content>
      <ion-list [inset]="true">
        <ion-grid>

          <!-- Lote -->
          <ion-row>
            <ion-col size="12">
              <ion-title>LOTE</ion-title>
              <ion-item>
                <ion-label position="stacked">SELECIONE UM LOTE *</ion-label>
                <ion-select (ionChange)="onLoteChange($event)" interface="action-sheet" placeholder="Selecione um Lote" required>
                  <ion-select-option *ngFor="let lote of lotes" [value]="lote.id">
                    {{ lote.fazendaNome }}
                  </ion-select-option>
                </ion-select>
              </ion-item>
            </ion-col>
          </ion-row>

          <!-- Temperatura -->
          <ion-row>
            <ion-col size="12">
              <ion-title>TEMPERATURA</ion-title>
            </ion-col>
            <ion-col size="6">
              <ion-item>
                <ion-label position="stacked">TEMPERATURA AMBIENTE (°C) *</ion-label>
                <ion-input type="number" [(ngModel)]="temperaturaAmbiente" required></ion-input>
              </ion-item>
            </ion-col>
            <ion-col size="6">
              <ion-item>
                <ion-label position="stacked">TEMPERATURA DO SOLO (°C) *</ion-label>
                <ion-input type="number" [(ngModel)]="temperaturaSolo" required></ion-input>
              </ion-item>
            </ion-col>
          </ion-row>

          <!-- Umidade -->
          <ion-row>
            <ion-col size="12">
              <ion-title>UMIDADE</ion-title>
            </ion-col>
            <ion-col size="6">
              <ion-item>
                <ion-label position="stacked">UMIDADE AMBIENTE (%) *</ion-label>
                <ion-input type="number" [(ngModel)]="umidadeAmbiente" required></ion-input>
              </ion-item>
            </ion-col>
            <ion-col size="6">
              <ion-item>
                <ion-label position="stacked">UMIDADE DO SOLO (%) *</ion-label>
                <ion-input type="number" [(ngModel)]="umidadeSolo" required></ion-input>
              </ion-item>
            </ion-col>
          </ion-row>

          <!-- Condições do Solo -->
          <ion-row>
            <ion-col size="12">
              <ion-title>CONDIÇÕES DO SOLO</ion-title>
            </ion-col>
            <ion-col size="6">
              <ion-item>
                <ion-label position="stacked">PH DO SOLO *</ion-label>
                <ion-input type="number" step="0.1" [(ngModel)]="phSolo" required></ion-input>
              </ion-item>
            </ion-col>
            <ion-col size="6">
              <ion-item>
                <ion-label position="stacked">ÍNDICE UV *</ion-label>
                <ion-input type="number" [(ngModel)]="indiceUV" required></ion-input>
              </ion-item>
            </ion-col>
          </ion-row>

          <!-- Botão -->
          <ion-row class="ion-justify-content-end">
            <ion-col size="6" size-md="4" class="ion-text-center" style="margin-top: 25px; margin-left: 10px;">
              <ion-button expand="block" type="submit" (click)="enviarDados()">ENVIAR</ion-button>
            </ion-col>
          </ion-row>

        </ion-grid>
      </ion-list>
    </ion-card-content>
  </ion-card>
</ion-content>
```





---

## 💻 **Hard Skills**

| Tecnologia / Metodologia | Nível de Proficiência (★) |
| ------------------------ | ------------------------- |
| **Scrum**                | ★★★★★★☆☆☆☆                |
| **PostgreSQL**           | ★★★★★★★★★★                |
| **Spring Boot (Java)**   | ★★★★★★★★☆☆                |
| **Angular / TypeScript** | ★★★★★★★☆☆☆                |
| **MongoDB**              | ★★★★★★☆☆☆☆                |
| **LGPD (prática)**       | ★★★★★★★☆☆☆                |

---


---

## 💻 **Hard Skills – Justificativas**

| Tecnologia / Metodologia | Justificativa                                                                                                                                                             |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Scrum**                | Participei de cerimônias ágeis como *daily*, *sprint review* e *planning*, contribuindo para entregas organizadas, embora ainda em evolução na facilitação de cerimônias. |
| **PostgreSQL**           | Domínio avançado na modelagem de dados, criação de procedures, views e queries complexas em ambientes de produção.                                                        |
| **Spring Boot (Java)**   | Desenvolvimento de APIs REST com segurança, integração com bancos de dados e uso de boas práticas do ecossistema Spring.                                                  |
| **Angular / TypeScript** | Atuação em interfaces interativas com formulários reativos, consumo de APIs e aplicação de boas práticas no front-end.                                                    |
| **MongoDB**              | Utilização para armazenamento não relacional e análise complementar de dados junto ao PostgreSQL, em projetos de monitoramento.                                           |
| **LGPD (prática)**       | Aplicação prática dos princípios da LGPD em sistemas, como anonimização de dados e controle de consentimento de usuários.                                                 |



---



## 🤝 **Soft Skills**

| Competência                | Nível de Desenvolvimento (★) |
| -------------------------- | ---------------------------- |
| **Comunicação**            | ★★★★★★★★★☆                   |
| **Responsabilidade**       | ★★★★★★☆☆☆☆                   |
| **Organização**            | ★★★★★★★☆☆☆                   |
| **Trabalho em equipe**     | ★★★★★★★★☆☆                   |
| **Resolução de problemas** | ★★★★★★★☆☆☆                   |

---



---

## 🤝 **Soft Skills – Justificativas**

| Competência                | Justificativa                                                                                                                 |
| -------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **Comunicação**            | Clareza na troca de informações com a equipe e stakeholders, facilitando entendimento técnico e alinhamento de expectativas.  |
| **Responsabilidade**       | Cumprimento de prazos e comprometimento com a qualidade das entregas, com espaço para melhorar a autogestão sob alta demanda. |
| **Organização**            | Estruturação lógica do código e uso de ferramentas de produtividade (como Trello e Git) para manter fluxos bem definidos.     |
| **Trabalho em equipe**     | Colaboração constante com desenvolvedores, designers e PO's, contribuindo com sugestões e apoio técnico em grupo.             |
| **Resolução de problemas** | Capacidade de analisar erros, realizar debug e propor soluções práticas tanto no back-end quanto no front-end.                |

---







##
