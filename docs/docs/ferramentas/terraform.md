# <img src="../../images/terraform-logo.png" alt="drawing" width="30"/> Terraform

## O que é

É uma ferramenta criada pela HashiCorp utilizada para automatizar o **provisionamento** e **gerenciamento** de recursos de infraestrutura em **nuvem**

## Onde usar

Em projetos em que se deseja provisionar recursos em nuvem alem de manter o controle de versão desta infra

## Como é aplicado

É utilizado via linha de comando, atravez do binário "terraform", muitas vezes abreviado (utilizando alias) para "tf".


=== "Comando "terraform plan -out plans""
    ![](../../images/terraform plan.png)

=== "Comando "tfp -out plans""
    ![](../../images/tfp.png)

Seus manifestos são escritos em HCL para a descrição dos recursos que se deseja provisionar

![](../../images/hcl.png)

## Estrutura

Um projeto com terraform geralmente é organizado da seguinte maneira:

![](../../images/terraform-tree.bmp)

Gerados automaticamente:

* .terraform
* .terraform.lock.hcl
* **terraform.tfstate**
* terraform.tfstate.backup

Criados pelo usuário:

* Pasta modules
* output.tf
* plans
* provider.tf
* terrafile.tf
* variables.tf

Os arquivos automáticos são referentes a metadados, destacando o terraform.tfstate, que armazena todo o gerenciamento de recursos existentes na nuvem.

Na pasta "modules" é onde armazenamos os manifestos hcl

O arquivo "plans" é opcional, mas recomendado. Através dele existe uma comparação entre o tfstate e os manifestos que desejamos aplicar, e então temos uma visão de recursos novos que serão construidos, do que será destruído e o que será atualizado. Podemos gerá-lo através do argumento "-out" no comando "terraform plan"

output.tf na raíz do projeto printa a informação desejada durante a execução na tela