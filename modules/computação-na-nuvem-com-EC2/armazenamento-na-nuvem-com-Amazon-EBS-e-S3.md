# Armazenamento na Nuvem com Amazon EBS e S3

## Amazon EBS
- Elastic Block Store(EBS): storage, altamente confiável, que pode ser anexado a uma instância EC2 como expansão de memória.
- Fornece armazanamento em bloco fiável, também conhecido como volumes ou discos rígidos.
- A memória que já vem na instância, é uma memória que comporta somente o sistema operacional.
- O EBS é como um HD externo para comportar novas features.
- Snapshot: permite backup e criação de novos volumes EBS. Ele é como uma foto instantânea do estado dos dados em nuvem, usada para backup, restauração e replicação rápida.

## Amazon S3 (Amazon Simple Storage Service)
- Serviço de armazenamento de objetos em nuvem
- Ideal para armazenar, organizar e recuperar grandes volumes de dados de forma segura e escalável.

    ### Classes de Storages
    - S3 Standard
    - S3 Standard IA
    - S3 One Zone - Infrequent access
    - S3 Glacier

- Regra do ciclo de vida: define a forma como o S3 gere os objetos durante o seu tempo de vida. O "Lifecycle" permite fazer a transição de objetos e migrar automaticamente para a classe Glacier.
- Para saber mais: https://aws.amazon.com/pt/s3/storage-classes/#topic-0