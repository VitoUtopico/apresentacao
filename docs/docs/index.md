# Infrastructure as Code (IaC)

Modelo de construção e gerenciamento de infraestrutura através de código intimamente ligado à **cultura DevOps** que permite o versionamento da infraestrutura, automatização nos deploys, em alguns casos o uso de uma **infraestrutura imutavel**, e ainda, em muitos casos, possibilidade de uso de comandos, tanto **declarativo** quanto **imperativo**

=== "Comando imperativo no kubernetes"
    ~~~bash
    $ kubectl run nginx --image nginx:latest -ns bananada --port 80
    ~~~

=== "Arquivo declarativo no kubernetes"
    ~~~yaml
    apiVersion: v1
    kind: Pod
    metadata:
      name: nxginx
      namespace: bananada
    template:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80  
    ~~~

## O que é

Segundo a [Red Hat](https://www.redhat.com/en/topics/automation/what-is-infrastructure-as-code-iac)
> "Infrastructure as Code (IaC) is the managing and provisioning of infrastructure through code instead of through manual processes."

## Onde usar

* Ambientes de **Cloud e On Premises** (pode variar de acordo com a ferramenta);
* Onde for necessário **reconstruir** uma determinada infra com **constância**;
* Em situações de **constantes modificações** de uma infra;
* Em casos em que se precise configurar todo um **parque de máquinas** em que a **configuração manual** possa se tornar algo **moroso**.

## Porque utilizar

A **repetição de processos manuais** pode levar a exaustão que pode levar ao **falhas**, portanto o processo automatizado evita esse tipo de falha humana, além de **liberar o profissional** para tarefas que dependam mais de conhecimento e raciocinio do que de tempo investido em um esforço mais "bruto"

## Como é aplicado

Através de **ferramentas** específicas que podem ser **mais ou menos especializadas** e que atendem **diferentes necessidades**
Exemplos dessas ferramentas:

* [Ansible](https://www.ansible.com/);
* [AWS CloudFormation](https://aws.amazon.com/pt/cloudformation/);
* [Chef](https://www.chef.io/);
* [Puppet](https://www.puppet.com/);
* [Saltstack](https://docs.saltproject.io/en/latest/contents.html);
* [Terraform](https://www.terraform.io/);
* [OpenTofu](https://opentofu.org/).

## Quem se beneficia

Pode variar muito em cada organização, mas aparentemente a tendência é:

* Desenvolve
    * DevOps Engineer
    * Cloud Engineer
    * Platform Engineer
    * SRE
* Utiliza
    * Dev
    * DS
    * DE