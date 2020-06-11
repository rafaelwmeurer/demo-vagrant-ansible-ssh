# Demo Vagrant SSH 

Importate:
- Ter a chave ssh gerada na sua máquina e não ter criado nenhum outra vm com o mesmo ip, para evitar erros na execução do playbook.


### Execute o comando

```
vagrant up
```

Com a máquina criada, basta agora executar o playbook que precisar.  

### Execute o comando (exemplo)

```
ansible-playbook -i roles/hosts roles/hosts
```

Este é apenas um exemplo, existe n formas de colocar inclusive o ip dentro do hosts de forma dinâmica, nesta caso está fixo.