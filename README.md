# Simulador de Transmissão Digital 📡

**Trabalho GB - Redes de Computadores II**  
**Universidade do Vale do Rio dos Sinos (UNISINOS)**  
**Data:** Novembro / 2026  

---

## 👥 Aluno

* **Thallis Gabriel de Mello da Silva:** Responsável geral pelo projeto.

---

## 🏗️ Arquitetura do Simulador

O simulador foi construído em **Python** (via Google Colab) e modela um enlace de comunicação digital ponta a ponta. A arquitetura divide-se nas seguintes etapas:

1. **Geração de Dados:** Conversão de mensagens de texto ASCII para arrays de bits (0s e 1s).
2. **Codificação de Linha:** Adaptação do sinal em banda base utilizando as técnicas **Manchester** e **AMI**.
3. **Modulação Digital:** Mapeamento de bits para símbolos complexos em três esquemas diferentes:
   * **BPSK** (1 bit/símbolo)
   * **QPSK** (2 bits/símbolo)
   * **16-QAM** (4 bits/símbolo - modulação de ordem superior)
4. **Modelagem de Canal:** 
   * **AWGN** (Ruído Branco Gaussiano Aditivo) com controle dinâmico de Relação Sinal-Ruído (SNR).
   * **Ruído de Rajada** (Fading severo e intermitente inserido no sinal).
5. **Recepção:** Demodulação com base nas regiões de decisão, decodificação reversa e cálculo rigoroso da Taxa de Erro de Bits (BER).

---

## ⚙️ Parâmetros do Experimento

Para garantir a validade estatística dos testes e a correta plotagem da curva de desempenho (BER x SNR), os seguintes parâmetros foram configurados no ensaio principal:

* **Tamanho da Amostra:** 100.000 bits processados por ensaio.
* **Repetições:** 5 ensaios independentes por configuração (cálculo de média para mitigar variância).
* **Variação de SNR:** 8 níveis distintos avaliados (0, 2, 4, 6, 8, 10, 12 e 14 dB).
* **Métricas Extraídas:** Taxa de Erro de Bits (BER) e Eficiência Espectral Nominal.

---

## 🚀 Como Executar

Todo o código foi agrupado em um notebook para facilitar a execução.

1. Faça o download do arquivo `Simulador_Redes_II.ipynb` que se encontra neste repositório.
2. Acesse (https://colab.research.google.com/).
3. Faça o upload do arquivo (`Arquivo > Fazer upload de notebook`).
4. No menu superior, clique em **Ambiente de execução > Executar tudo**.
5. O final da execução imprimirá os logs de erro por SNR, a tabela de eficiência espectral e plotará a curva comparativa `BER x SNR`.

---

## 🎥 Vídeo de Apresentação

Neste vídeo de 5 minutos, faço a demonstração a execução do código no Colab, valido os resultados e explico a análise comparativa entre as três modulações e o trade-off de eficiência espectral.

🔗 **Link para o Vídeo:** https://youtu.be/Q7kfJd0oYgg
