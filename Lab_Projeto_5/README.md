# Explorando o Microsoft Copilot e OpenAi

## Proposta

O objetivo aqui é explorar os recursos do **Microsoft Copilot**/

Esses recursos podem ser descritos, genericamente, como uso para tarefas generativas da inteligencia artificial. No primeiro tópico iremos testar diferentes inputs na forma de texto em linguagem coloquial no **Microsoft Copilot**.

Vamos seguir a documentação do **Microsoft Learn** e ao longo do texto serão feitos comentários sobre o processo para esclarecer possíveis dúvidas. A referencia principal é a documentação:

- [Explore generative AI with Microsoft Copilot](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/12-generative-ai.html)
- [Explore Azure OpenAI](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/13-azure-openai.html)
- [Explore content filters in Azure OpenAI](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/14-azure-openai-content-filters.html)

Antes de começar é importante notar que para seguir esse passo a passo é necessário configurar uma conta no Microsoft Azure e criar um workspace. Para tal, a seguinte lista lista de recursos pode ser usada como guia:

- [Criar serviços incluídos com a conta gratuita do Azure](https://learn.microsoft.com/pt-br/azure/cost-management-billing/manage/create-free-services).
- [O que é um workspace do Azure Machine Learning?](https://learn.microsoft.com/pt-br/azure/machine-learning/concept-workspace?view=azureml-api-2)
- [Explore Azure AI Services](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/02-content-safety.html)

## Explorando o Microsoft Copilot

O **Microsoft Copilot** é uma ferramente criada partindo dos chamados LLM (large language models) treinados para geração de informações na forma de texto, imagens, etc. Para tal, o modelo de **deep learning** é treinado em uma grande quantidade de informações e, de forma procedural, consegue criar novas informações usando os padrões de texto, imagem, etc. aprendidos. A grande vantagem única desse tipo de modelo é o fato de poder realizar consultas utilizando de language natural e obter as informações desejadas nessa mesma forma. Isso é uma grande diferença no caso do laboratório anterior onde as consultas (queries) e as respostas eram em JSON. Vamos explorar algumas perguntas/respostas no **Microsoft Copilot** seguindo como base os exemplos da documentação

### Pergunta sobre viagem

#### Pergunta

Quais os 3 prós e contras de se viajam para o Rio de Janeiro?

#### Resposta

Claro! O **Rio de Janeiro** é uma cidade vibrante e cheia de encantos. Aqui estão **três prós e três contras** para considerar ao planejar sua viagem:

**Prós**:

1. **Belezas Naturais e Praias**: O Rio é famoso por suas praias icônicas, como **Copacabana** e **Ipanema**. Aproveite o sol, o mar e as paisagens deslumbrantes.
2. **Cultura e Vida Noturna**: A **Lapa** é o coração pulsante da cultura carioca, com bares, boates e restaurantes animados. Experimente a culinária local e internacional!
3. **Transporte Público Eficiente**: O **metrô** é uma opção inteligente para se locomover pela cidade com rapidez e eficiência. Evite o trânsito caótico e chegue aos seus destinos sem estresse ¹³.

**Contras**:

4. **Segurança**: Como em todas as grandes cidades, tome precauções. Evite usar o celular em locais movimentados e caminhe por áreas bem iluminadas à noite. Opte por táxis ou Uber para voltar para casa.
5. **Tráfego Pesado**: O trânsito no Rio pode ser caótico, especialmente nas horas de pico. Considere usar o metrô para evitar o congestionamento ²³.
6. **Chuvas de Verão**: De dezembro a março, o Rio enfrenta tempestades. Se possível, visite nos meses de abril e maio para aproveitar o calor e evitar a umidade excessiva ¹.Lembre-se de aproveitar ao máximo sua viagem e explorar todas as maravilhas que a Cidade Maravilhosa tem a oferecer! 🌴🌊🏖️.

**Source:**
- Conversation with Bing, 4/10/2024
- (1) 11 dicas que você precisa saber antes de viajar para o Rio de Janeiro. https://ddrio.com/11-dicas-que-voce-precisa-saber-antes-de-viajar-para-o-rio-de-janeiro/.
- (2) 10 coisas que você precisa saber antes de visitar o Rio de Janeiro. https://caminhoslanguages.com/br/blog/things-to-know-before-going-to-rio-de-janeiro/.
- (3) Morar no Rio de Janeiro 【2024】 - Morarr.com. https://morarr.com/morar-no-rio-de-janeiro/.
- (4) Roteiro de viagem para o Rio de Janeiro para 4, 7 ou mais dias. https://www.viciadaemviajar.com/como-montar-seu-roteiro-de-viagem-para-o-rio-de-janeiro/.
- (5) Como visitar o Rio de Janeiro com segurança - Viaje na Viagem. https://www.viajenaviagem.com/destino/rio-de-janeiro/seguranca/.
- F(6) Getty Images. https://www.gettyimages.com/detail/photo/sunny-view-onto-corcovado-and-sugarloaf-royalty-free-image/450803003.

### Geração de imagens

#### Pergunta

Crie a imagem de um gato comendo uma maça

#### Resposta

![img](../Imagens/Lab_Projeto_5_imagens/img1.jpeg)
![img](../Imagens/Lab_Projeto_5_imagens/img2.jpeg)
![img](../Imagens/Lab_Projeto_5_imagens/img3.jpeg)
![img](../Imagens/Lab_Projeto_5_imagens/img4.jpeg)

### Geração de código

#### Pergunta

Escreve o código em Python para procurar um número em um lista. A lista é ordenada, use o método de procura binário.

#### Resposta

Claro! Aqui está um exemplo de código Python que realiza uma pesquisa binária em uma lista ordenada:

```python
def pesquisa_binaria(lista, alvo):
    esquerda, direita = 0, len(lista) - 1

    while esquerda <= direita:
        meio = (esquerda + direita) // 2
        valor_meio = lista[meio]

        if valor_meio == alvo:
            return meio  # Encontrou o valor na posição 'meio'
        elif valor_meio < alvo:
            esquerda = meio + 1  # Procura na metade direita
        else:
            direita = meio - 1  # Procura na metade esquerda

    return -1  # Valor não encontrado na lista

# Exemplo de uso
minha_lista_ordenada = [10, 20, 30, 40, 50, 60, 70, 80, 90]
numero_procurado = 50

resultado = pesquisa_binaria(minha_lista_ordenada, numero_procurado)
if resultado != -1:
    print(f"O número {numero_procurado} foi encontrado na posição {resultado}.")
else:
    print(f"O número {numero_procurado} não está na lista.")
```

Neste código, a função `pesquisa_binaria` recebe uma lista ordenada e um número alvo como argumentos. Ela utiliza o método de "dividir e conquistar" para encontrar a posição do valor na lista. Se o valor não estiver presente, a função retorna -1. Lembre-se de adaptar a lista e o número alvo conforme sua necessidade. 🍀

**Source:**
- Conversation with Bing, 4/10/2024
- (1) Pesquisa binária em Python – Como escrever o algoritmo de pesquisa .... https://www.freecodecamp.org/portuguese/news/pesquisa-binaria-em-python-como-escrever-o-algoritmo-de-pesquisa-binaria-e-exemplos/.
- (2) algoritmo - Algoritmo de busca binária em Python - Stack Overflow em .... https://bing.com/search?q=c%c3%b3digo+Python+procurar+n%c3%bamero+lista+ordenada+m%c3%a9todo+procura+bin%c3%a1rio.
- (3) algoritmo - Algoritmo de busca binária em Python - Stack Overflow em .... https://pt.stackoverflow.com/questions/388284/algor%c3%adtmo-de-busca-bin%c3%a1ria-em-python.
- (4) Algoritmo de pesquisa binária em Python (explicado) - ICHI.PRO. https://ichi.pro/pt/algoritmo-de-pesquisa-binaria-em-python-explicado-218488926085941.
- (5) Programa para pesquisa binária em Python - Go Coding. https://gocoding.org/pt/programa-para-busca-bin%C3%A1ria-em-python/.

### Conclusão sobre o Microsoft Copilot

Podemos ver que as tarefas foram realizadas de forma satisfatória. Os prós e contras sobra a viagem são razoáveis além de apontar referencias para as informações. As imagens geradas são bonitas e realistas, mesmo sendo uma descrição que não é considerada usual. O código em Python gerado está correto e parece seguir os padrões da linguagem.

Sobre o serviço **Azure OpenAI**, podemos perguntar ao Copilot para nos dar um pequeno resumo.

>O **Serviço OpenAI do Azure** fornece acesso à **API REST** para modelos de linguagem avançados do **OpenAI**, incluindo as séries de modelos **GPT-4**, **GPT-4-Turbo com Visão**, **GPT-3.5-Turbo** e **Embeddings**. Esses modelos podem ser adaptados facilmente para tarefas específicas, como geração de conteúdo, sumarização, reconhecimento de imagem, pesquisa semântica e tradução de linguagem natural para código. Os usuários podem acessar o serviço por meio de APIs REST, SDK do Python ou pela interface baseada na Web no **Estúdio do OpenAI do Azure**¹.
>Aqui estão alguns pontos-chave sobre o **Serviço OpenAI do Azure**:
>
>- **Modelos Disponíveis**:
>    - Série **GPT-4** (incluindo **GPT-4 Turbo com Visão**)
>    - Série **GPT-3.5-Turbo**
>    - Série **Embeddings**
>    - Saiba mais em nossa página de [Modelos](https://learn.microsoft.com/pt-br/azure/ai-services/openai/overview).
>- **Ajuste Fino (versão prévia)**:
>    - É possível ajustar o modelo **GPT-3.5-Turbo (0613)** com os nomes de código **babbage-002** e **davinci-002**.
>- **Preço**:
>    - Os detalhes de preços estão disponíveis [aqui](https://learn.microsoft.com/pt-br/azure/ai-services/openai/overview).
>- **Suporte à Rede Virtual e Link Privado**:
>    - Sim, a menos que você use o **OpenAI do Azure** em seus próprios dados.
>- **Identidade Gerenciada**:
>    - Sim, via **ID do Microsoft**.
>- **Experiência de Interface do Usuário**:
>    - **Portal do Azure** para gerenciamento de conta e recursos.
>    - **Azure OpenAI Service Studio** para exploração de modelos e ajuste fino.
>- **IA Responsável**:
>    - A Microsoft está comprometida com o avanço da IA orientada por princípios que colocam as pessoas em primeiro lugar. Modelos generativos, como os disponíveis no **OpenAI do Azure**, têm benefícios potenciais significativos, mas também o potencial de gerar conteúdo incorreto ou prejudicial. A Microsoft implementou medidas para proteger contra abusos e danos não intencionais, incluindo diretrizes de uso responsável e filtros de conteúdo¹.
>
>Atualmente, o acesso ao **OpenAI do Azure** é limitado enquanto navegamos pela alta demanda, melhorias futuras de produtos e nosso compromisso com a **IA responsável**. Estamos trabalhando com clientes que possuem parceria existente com a Microsoft, casos de uso de baixo risco e aqueles comprometidos em incorporar mitigações¹.
>
>Source: Conversation with Bing, 4/10/2024
>- (1) O que é o Serviço OpenAI do Azure? - Azure AI services. https://learn.microsoft.com/pt-br/azure/ai-services/openai/overview.
>- (2) Conheça tudo sobre o Serviço OpenAI do Azure - Green Tecnologia. https://www.green.com.br/blog/conheca-tudo-sobre-o-servico-openai-do-azure/.
>- (3) Serviço OpenAI do Azure – Modelos Avançados de Idioma | Microsoft Azure. https://azure.microsoft.com/pt-br/products/ai-services/openai-service.
>- (4) O que é o Azure OpenAI? E como vai influenciar o seu negócio?. https://www.alvo.com/blog/como-e-que-o-azure-openai-e-a-alvo-podem-fazer-evoluir-o-seu-negocio/.
>- (5) O que é o Serviço Azure OpenAI? - Azure AI services. https://learn.microsoft.com/pt-pt/azure/ai-services/openai/overview.

Como podemos ver, o **Azure OpenAI** permite criar um modelo similar ao **Copilot** com customizações. Isso é similar aos laboratórios anteriores onde criamos modelos e customizamos as soluções ou realizamos o treinamento deles com dados específicos. Infelizmente, atualmente esse recurso não é aberto ao publico, o que mostra que ele ainda está em desenvolvimento o que mostra a alta demanda do mercado atual o que é condizente com o alto nível de processamento necessário para tal implementação.