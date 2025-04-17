# Projeto CartPole 3D (Simulado) com Visualização Aprimorada

Este projeto visa criar uma visualização rica e envolvente do clássico problema do CartPole, um ambiente fundamental no aprendizado por reforço. Em vez da tradicional representação 2D, exploramos uma abordagem que simula um cenário 3D rotativo para proporcionar uma compreensão mais intuitiva da dinâmica do sistema.

## Demonstração

![Animação CartPole 3D](http://googleusercontent.com/image_generation_content/0)

## Tecnologias Utilizadas

* **Python**: A linguagem de programação principal para o desenvolvimento do projeto.
* **OpenAI Gym (`gym`)**: Utilizado para acessar o ambiente de simulação do CartPole (`CartPole-v1`).
* **NumPy**: Fundamental para realizar operações numéricas eficientes, especialmente no cálculo das posições dos elementos e na simulação da rotação do cubo.
* **Matplotlib**: A principal biblioteca de visualização em Python.
    * `matplotlib.pyplot`: Usado para criar a figura, os eixos e os diferentes elementos gráficos (retângulos, círculos, linhas).
    * `matplotlib.animation`: Essencial para gerar a animação quadro a quadro, atualizando as posições dos objetos ao longo do tempo.
    * `matplotlib.patches`: Módulo utilizado para criar formas geométricas como `Rectangle` (para o carrinho e o chão) e `Circle` (para as rodas, junta e massa do pêndulo).
    * `matplotlib.colors`: Pode ser usado para definir esquemas de cores e criar gradientes (embora neste projeto as cores sejam definidas diretamente).
* **`IPython.display.HTML`**: Utilizado em ambientes Jupyter Notebook ou Google Colab para incorporar e exibir a animação diretamente na saída do notebook.

## Funcionalidades Principais

* **Simulação de Cenário em Cubo 3D Rotativo**: Uma ilusão de um cubo tridimensional girando lateralmente, proporcionando uma sensação de profundidade e diferentes perspectivas da cena.
* **Visualização Detalhada do Carrinho e Haste**: Representação aprimorada do carrinho com realces e rodas detalhadas, e da haste (pêndulo) com uma junta de conexão e massa definida.
* **Chão Ancorado**: Adição de um elemento visual representando o chão para evitar a sensação de que o carrinho está flutuando.
* **Animação Fluida**: Geração da animação com um intervalo adequado entre os frames para garantir um movimento suave.

## Como Executar

1.  **Certifique-se de ter o Python instalado em seu sistema.**
2.  **Instale as bibliotecas necessárias:**
    ```bash
    pip install gym numpy matplotlib ipython
    ```
3.  **Clone este repositório (se o código estiver em um repositório).**
4.  **Execute o script Python (ou o notebook Jupyter) que contém o código.**

   * Se estiver usando um notebook Jupyter, a animação deverá ser exibida diretamente na saída da célula após a execução.
   * O código também inclui uma opção para salvar a animação como um arquivo GIF (`ani.save('nome_do_arquivo.gif', writer='pillow', fps=30)`), caso você queira gerar um arquivo de vídeo. Certifique-se de ter o `Pillow` instalado (`pip install Pillow`) se quiser usar o writer 'pillow'.

## Observações sobre o Código

* A linha `mpl.rcParams['animation.embed_limit'] = 50.0` aumenta o limite padrão para permitir que animações maiores sejam incorporadas em notebooks.
* O ambiente do CartPole é criado e resetado usando as funções do `gym`.
* A figura e os eixos são configurados com uma proporção fixa e limites iniciais para enquadrar a cena da animação.
* A simulação da rotação do cubo é feita manipulando as coordenadas 2D das arestas do cubo ao longo do tempo.
* Os elementos do carrinho e da haste são criados como objetos `Rectangle` e `Circle` do Matplotlib, com cores e detalhes aprimorados.
* A função `update` é responsável por atualizar a posição do carrinho, do pêndulo e a rotação do cubo a cada frame da animação.
* A função `init` é usada para inicializar o estado da animação.
* `animation.FuncAnimation` cria a animação chamando repetidamente a função `update`.
* `HTML(ani.to_jshtml())` (em ambientes Jupyter) exibe a animação interativamente.

## Próximos Passos (Ideias para Melhorias)

* Adicionar informações textuais dinâmicas na tela (por exemplo, ângulo do pêndulo, ação tomada).
* Experimentar com diferentes estilos visuais e esquemas de cores.
* Implementar algoritmos de aprendizado por reforço para controlar o CartPole e visualizar o comportamento do agente.
* Explorar a criação de uma simulação 3D mais genuína usando bibliotecas gráficas 3D.

Sinta-se à vontade para explorar o código, contribuir com melhorias e compartilhar suas ideias!
