<template>
  <v-container fill-height fluid grid-list-xl>
    <v-layout wrap>
      <v-flex md12 sm12 lg12>
        <material-card color="primary" title="Cadastro de Canvas">
          <v-form ref="form" v-model="valid" lazy-validation>
            <template>
              <v-stepper v-model="passo" alt-labels>
                <v-stepper-header>
                  <v-stepper-step :complete="passo > 1" step="1">Primeira Etapa</v-stepper-step>
                  <v-divider />
                  <v-stepper-step :complete="passo > 2" step="2">Segunda Etapa</v-stepper-step>
                  <v-divider />
                  <v-stepper-step :complete="passo > 3" step="3">Terceira Etapa</v-stepper-step>
                </v-stepper-header>
                <v-stepper-items>
                    <!-- primeiro passo -->
                  <v-stepper-content step="1">
                    <v-card class="mb-5" height="100%">
                  <v-flex xs12 sm6 md8>
                       <v-text-field
                      label="Nome do Projeto"
                      placeholder="Qual será o nome do seu projeto?"
                      ></v-text-field>
                      </v-flex>
                        <v-flex xs12>
                        <v-textarea
                          label="Proposta de Valor"
                          placeholder="Informe a sua proposta de valor"
                          hint="Alguma dúvida? Clica no ícone de interrogação!"
                        >
                          <template v-slot:append-outer>
                              <v-btn fab dark small color="primary" @click="openModalProposta()">
                         <v-icon dark>mdi-help</v-icon>
                         </v-btn>
                          </template>
                        </v-textarea>
                      </v-flex>
                      <v-flex xs12>
                        <v-textarea
                          label="Segmento de Clientes"
                          placeholder="Informe o seu segmento de Clientes"
                          hint="Alguma dúvida? Clica no ícone de interrogação!"
                        >
                        <template v-slot:append-outer>
                              <v-btn fab dark small color="primary" @click="openModalSegmento()">
                         <v-icon dark>mdi-help</v-icon>
                         </v-btn>
                          </template>
                        </v-textarea>
                      </v-flex>
                      <v-flex xs12>
                        <v-textarea
                          label="Relacionamento com o Clientes"
                          placeholder="Informe o seu relacionamento de clientes"
                          hint="Alguma dúvida? Clica no ícone de interrogação!"
                        >
                          <template v-slot:append-outer>
                              <v-btn fab dark small color="primary" @click="openModalRelacionamento()">
                         <v-icon dark>mdi-help</v-icon>
                         </v-btn>
                          </template>
                        </v-textarea>
                      </v-flex>
                      <v-flex xs12>
                        <v-textarea
                          label="Canais de Distribuição"
                          placeholder="Informe os seus canais de distribuição"
                          hint="Alguma dúvida? Clica no ícone de interrogação!"
                        >
                          <template v-slot:append-outer>
                              <v-btn fab dark small color="primary" @click="openModalCanal()">
                         <v-icon dark>mdi-help</v-icon>
                         </v-btn>
                          </template>
                        </v-textarea>
                      </v-flex>
                    </v-card>
                    <v-btn color="primary" @click="passo = 2">Continuar</v-btn>
                    <v-btn color="red darken-1" to="/">Cancelar</v-btn>
                  </v-stepper-content>
                  <!-- passo dois -->
                   <v-stepper-content step="2">
                    <v-card class="mb-5" height="100%">
                      <v-flex xs12>
                        <v-textarea
                          label="Atividades Chaves"
                          placeholder="Informe as suas atividades chave"
                          hint="Alguma dúvida? Clica no ícone de interrogação!"
                        >
                         <template v-slot:append-outer>
                              <v-btn fab dark small color="primary" @click="openModalAtividades()">
                         <v-icon dark>mdi-help</v-icon>
                         </v-btn>
                          </template>
                        </v-textarea>
                      </v-flex>
                      <v-flex xs12>
                        <v-textarea
                          label="Recursos Chave"
                          placeholder="Informe os seus recursos chave"
                          hint="Alguma dúvida? Clica no ícone de interrogação!"
                        >
                         <template v-slot:append-outer>
                              <v-btn fab dark small color="primary" @click="openModalRecursos()">
                         <v-icon dark>mdi-help</v-icon>
                         </v-btn>
                          </template>
                        </v-textarea>
                      </v-flex>
                      <v-flex xs12>
                        <v-textarea
                          label="Parceiros Chave"
                          placeholder="Informe os seus parceiros chave"
                          hint="Alguma dúvida? Clica no ícone de interrogação!"
                        >
                        <template v-slot:append-outer>
                              <v-btn fab dark small color="primary" @click="openModalParceiros()">
                         <v-icon dark>mdi-help</v-icon>
                         </v-btn>
                          </template>
                        </v-textarea>
                      </v-flex>
                    </v-card>
                    <v-btn color="primary" @click="passo = 3">Continuar</v-btn>
                     <v-btn color="red darken-1" @click="passo = 1">Voltar</v-btn>
                  </v-stepper-content>
                <v-stepper-content step="3">
                    <v-card class="mb-5" height="100%">
                      <v-flex xs12>
                        <v-textarea
                          label="Fonte de Receita"
                          placeholder="Informe a sua fonte de receita"
                          hint="Alguma dúvida? Clica no ícone de interrogação!"
                        >
                          <template v-slot:append-outer>
                              <v-btn fab dark small color="primary" @click="openModalReceita()">
                         <v-icon dark>mdi-help</v-icon>
                         </v-btn>
                          </template>
                        </v-textarea>
                      </v-flex>
                      <v-flex xs12>
                        <v-textarea
                          label="Estrutura de Custos"
                          placeholder="Informe a sua estrutura de custos"
                          hint="Alguma dúvida? Clica no ícone de interrogação!"
                        >
                          <template v-slot:append-outer>
                              <v-btn fab dark small color="primary" @click="openModalCustos()">
                         <v-icon dark>mdi-help</v-icon>
                         </v-btn>
                          </template>
                        </v-textarea>
                      </v-flex>
                    </v-card>
                    <v-btn color="primary" to="/">Cancelar</v-btn>
                     <v-btn color="red darken-1" @click="passo = 2">Voltar</v-btn>
                     <v-btn color="success" @click="passo = 2">Cadastrar</v-btn>
                  </v-stepper-content>
                </v-stepper-items>
              </v-stepper>
            </template>
          </v-form>
          <!-- cadastrado com sucesso -->
          <v-snackbar v-model="snackbar" :timeout="timeout" color="success" top>
            {{ textoCadastro }}
            <v-btn flat @click="snackbar = false">
              <v-icon left>mdi-close-circle</v-icon>
            </v-btn>
          </v-snackbar>
        </material-card>
      </v-flex>
       <v-dialog
        v-model="modalProposta"
        persistent
        max-width="600">
        <v-card>
        <v-card-title
          class="headline grey lighten-2"
          primary-title
        >
          O que é Proposta de Valor?
        </v-card-title>
        <v-card-text style="text-align: justify">
            Nesta parte são descritas as soluções que a empresa propõe a oferecer para resolver os problemas de seus clientes. <v-spacer/>
            Que valor será entregue para o segmento de clientes? 
            Quais são os problemas dos clientes que a empresa ajuda a resolver? 
            Quais são os produtos e serviços que são entregues para cada segmento de clientes? 
            Que necessidades dos clientes estão sendo atendidas?        
            </v-card-text>
        <v-divider></v-divider>
            <v-btn
              color="success"
              flat
              @click="modalProposta = false">
              Ok, entendi!
            </v-btn>
        </v-card>
      </v-dialog>
    <v-dialog
        v-model="modalSegmento"
        persistent
        max-width="600">
        <v-card>
        <v-card-title
          class="headline grey lighten-2"
          primary-title
        >
          O que é Segmento de Clientes?
        </v-card-title>
        <v-card-text style="text-align: justify">
            Seus clientes podem ser pessoas físicas e/ou empresas e, se necessário, 
            você pode trabalhar com mais de um público-alvo. Lembre-se de agrupar os clientes com o mesmo perfil.  <v-spacer/>          
            Para quem está sendo criado valor? Quem são os clientes mais importantes?        
            </v-card-text>
        <v-divider></v-divider>
            <v-btn
              color="success"
              flat
              @click="modalSegmento = false">
              Ok, entendi!
            </v-btn>
        </v-card>
      </v-dialog>
      <v-dialog
        v-model="modalRelacionamento"
        persistent
        max-width="600">
        <v-card>
        <v-card-title
          class="headline grey lighten-2"
          primary-title
        >
          O que é Relacionamento com o Cliente?
        </v-card-title>
        <v-card-text style="text-align: justify">
            Aqui, você precisa definir se o seu atendimento será por meio de uma página de perguntas e respostas, 
            interação humana, chatbot, comunidades no Facebook etc. <v-spacer/>
            Que tipo de relacionamento cada segmento de clientes espera de você?
            Quais os custos desse atendimento?
            </v-card-text>
        <v-divider></v-divider>
            <v-btn
              color="success"
              flat
              @click="modalRelacionamento = false">
              Ok, entendi!
            </v-btn>
        </v-card>
      </v-dialog>
    <v-dialog
        v-model="modalAtividades"
        persistent
        max-width="600">
        <v-card>
        <v-card-title
          class="headline grey lighten-2"
          primary-title
        >
          O que são as Atividades Chave?
        </v-card-title>
        <v-card-text style="text-align: justify">
           As atividades-chave são aquelas essenciais para manter a empresa funcionando e entregando todo o valor prometido. <v-spacer/>
           Alguns exemplos são: marketing, gerenciamento de redes sociais, criação de conteúdo audiovisual etc.
            </v-card-text>
        <v-divider></v-divider>
            <v-btn
              color="success"
              flat
              @click="modalAtividades = false">
              Ok, entendi!
            </v-btn>
        </v-card>
      </v-dialog>
          <v-dialog
        v-model="modalCanal"
        persistent
        max-width="600">
        <v-card>
        <v-card-title
          class="headline grey lighten-2"
          primary-title
        >
          O que são os Canais de Distribuição?
        </v-card-title>
        <v-card-text style="text-align: justify">
            Agora que você já sabe o que entrega e para quem entrega, chegou a hora de definir COMO você entrega. <v-spacer/>
            Como o cliente compra e recebe o produto/serviço?
            Em quais canais você pretende atuar para encaminhar vendas e solucionar eventuais problemas do consumidor em relação à sua empresa?<v-spacer/>
            Alguns exemplos de canais são Correios, redes sociais, Whatsapp e 0800 (SAC).
            </v-card-text>
        <v-divider></v-divider>
            <v-btn
              color="success"
              flat
              @click="modalCanal = false">
              Ok, entendi!
            </v-btn>
        </v-card>
      </v-dialog>
     <v-dialog
        v-model="modalRecursos"
        persistent
        max-width="600">
        <v-card>
        <v-card-title
          class="headline grey lighten-2"
          primary-title
        >
          O que são os Recursos Chave?
        </v-card-title>
        <v-card-text style="text-align: justify">
            Os recursos principais dizem respeito, basicamente, a tudo aquilo que a sua operação necessita para realizar as atividades-chave.
            Eles podem ser financeiros, físicos ou até humanos. <v-spacer/>
              <strong
              class="tertiary--text"
              style="font-size: 16px !important"> Exemplos: 
                </strong> prensas térmicas, computadores, gerente de marketing etc.
            </v-card-text>
        <v-divider></v-divider>
            <v-btn
              color="success"
              flat
              @click="modalRecursos = false">
              Ok, entendi!
            </v-btn>
        </v-card>
      </v-dialog>
       <v-dialog
        v-model="modalParceiros"
        persistent
        max-width="600">
        <v-card>
        <v-card-title
          class="headline grey lighten-2"
          primary-title
        >
          O que são os Parceiros Chave?
        </v-card-title>
        <v-card-text style="text-align: justify">
            As parcerias principais são alianças de negócio que você fará com fornecedores e outros parceiros. <v-spacer/>
            Quais são seus principais fornecedores?
            Quais das atividades-chave são executadas por parceiros?
            Quais recursos principais você está buscando fora da empresa? <v-spacer/>
            <strong
              class="tertiary--text"
              style="font-size: 16px !important"> Exemplo: 
                </strong>
            Terceirização, muitas empresas tem a necessidade de terceirizar determinados serviços que não são 
            sua atividade principal, como por exemplo, um escritório de contabilidade ou uma empresa de consultoria.
            </v-card-text>
        <v-divider></v-divider>
            <v-btn
              color="success"
              flat
              @click="modalParceiros = false">
              Ok, entendi!
            </v-btn>
        </v-card>
      </v-dialog>
    <v-dialog
        v-model="modalReceita"
        persistent
        max-width="600">
        <v-card>
        <v-card-title
          class="headline grey lighten-2"
          primary-title
        >
          O que é a Fonte de Receita?
        </v-card-title>
        <v-card-text style="text-align: justify">
            Como a sua empresa gera receita? Esta é a pergunta a ser respondida aqui. Dependendo do modelo de negócios, 
            você pode ter diversas fontes de receita.<v-spacer/>
            Por exemplo: “minha empresa gera receita vendendo produtos e prestando consultorias sobre o mercado” 
            ou “minha empresa gera receita por um sistema de assinaturas mensais”.
            </v-card-text>
        <v-divider></v-divider>
            <v-btn
              color="success"
              flat
              @click="modalReceita = false">
              Ok, entendi!
            </v-btn>
        </v-card>
      </v-dialog>
        <v-dialog
        v-model="modalCustos"
        persistent
        max-width="600">
        <v-card>
        <v-card-title
          class="headline grey lighten-2"
          primary-title
        >
          O que é a Estrutura de Custos?
        </v-card-title>
        <v-card-text style="text-align: justify">
            Aqui, você preencherá todos os custos relevantes necessários para o seu modelo de negócios funcionar. <v-spacer/>
            Esses custos podem ser fixos ou variáveis (aluguel, softwares, salários, manutenção de maquinaria, 
            campanhas de marketing etc).
            </v-card-text>
        <v-divider></v-divider>
            <v-btn
              color="success"
              flat
              @click="modalCustos = false">
              Ok, entendi!
            </v-btn>
        </v-card>
      </v-dialog>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      row: null,
      passo: 0,
      snackbar: false,
      textoCadastro: "Cadastrado com sucesso!",
      timeout: 4000,
      modalProposta: false,
      modalSegmento: false,
      modalRelacionamento: false,
      modalCanal: false,
      modalAtividades: false,
      modalRecursos: false,
      modalParceiros: false,
      modalReceita: false,
      modalCustos: false
    };
  },
  methods: {
      openModalProposta(){
          this.modalProposta = true
      },
      openModalSegmento(){
          this.modalSegmento = true
      },
      openModalRelacionamento(){
          this.modalRelacionamento = true
      },
      openModalCanal(){
          this.modalCanal = true
      },
      openModalAtividades(){
          this.modalAtividades = true
      },
      openModalRecursos(){
          this.modalRecursos = true
      },
      openModalParceiros(){
          this.modalParceiros = true
      },
      openModalReceita(){
          this.modalReceita = true
      },
      openModalCustos(){
          this.modalCustos = true
      }
      
  },
};
</script>
