# Amazon ELastic File System (Amazon EFS)

É um sistema de arquivos escalável usado com os serviços de nuvem AWS e recursos locais. O Amazon EFS expande e retrai automaticamente de acordo com o uso.  
Ele pode dimensionar sob demanda para petabytes sem interromper os aplicativos.

## Comparação entre EBS e EFS

### EBS
 - Armazena dados em uma **única** Zona de Disponibilidade
 - PAra anexar instancias EC2 a um volume EBS, ambos devem residir na mesma Zona de Disponibilidade

### EFS
- Armazena dados em várias Zonas de Disponibilidade e entre elas
- O armazenamento duplicado permite que voce acesse dados simultaneamente de todas as Zonas de Disponibilidade
- Os servidores locais podem acessar o EFS usando o AWS Direct Connect

