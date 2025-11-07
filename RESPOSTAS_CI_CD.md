# Aula Prática — Integração Contínua (CI) com GitHub Actions - Respostas

## 1. Introdução

| Pergunta | Resposta |
| :--- | :--- |
| **1. O que é CI/CD e por que é importante?** | **CI (Continuous Integration):** Integrar código frequentemente e testar a cada push. **CD (Continuous Delivery/Deployment):** Automatizar a entrega ou publicação do software. **Importância:** Crucial para detectar erros cedo e acelerar a entrega. |
| **2. Em qual pasta os workflows do GitHub ficam armazenados?** | Na pasta: `.github/workflows/`. |

## Etapa 3 - Verificando o pipeline

1.  **O que aparece no log do GitHub Actions após a execução?**
    * Na etapa "Executar script", aparece a saída do `python main.py`: `Hello CI/CD!`
2.  **O que acontece se alterar o código e fizer novo push?**
    * O *workflow* será **automaticamente disparado** novamente, pois o evento `on: push` está configurado para a branch `main`.

## Etapa 4 - Introduzindo um teste automatizado (extra)

**Pergunta extra: O que acontece se um teste falhar?**
* Se um teste falhar, o *step* "Executar testes" no GitHub Actions irá **falhar**, e o *pipeline* inteiro será marcado com um status **vermelho (Failure)**.

## 4. Para finalizar

* **Como o GitHub Actions ajuda a detectar erros cedo?**
    * Rodando testes, *linting* (verificação de estilo) e *builds* **automaticamente em cada *push***, o Actions detecta erros de integração e falhas de testes unitários imediatamente.
* **Quais seriam exemplos reais de CI/CD em projetos web ou mobile?**
    * **Web:** CI (Rodar testes); CD (Deploy automático para ambiente de staging).
    * **Mobile:** CI (Compilar o código e rodar testes); CD (Gerar o arquivo `.apk` ou `.ipa` e distribuir para testadores automaticamente).
* **Como o *deploy* automático poderia ser feito a partir deste *pipeline*?**
    * Adicionando um novo *step* com uma **Action de *deploy*** (AWS/Azure/GCP) que faz a autenticação e executa os comandos para publicar o código na nuvem.

---
