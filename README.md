# Olá, Mundo!
 primeiro repositório do curso de Gustavo Guanabara sobre Git e github.

 Durante uma aula ao vivo.
CREATE database geventos;

use geventos;

-- Criando a tabela usuarios
CREATE TABLE `geventos`.`tbusuarios` (
  `iduser` INT NOT NULL AUTO_INCREMENT,
  `Nome` VARCHAR(45) NOT NULL,
  `Fone` VARCHAR(45) NOT NULL,
  `Login` VARCHAR(45) NOT NULL,
  `Senha` VARCHAR(45) NOT NULL,
  `Perfil` VARCHAR(10) NULL,
  PRIMARY KEY (`iduser`));
  
  -- Criando a tabela Eventos
  
  CREATE TABLE `geventos`.`tbeventos` (
  `id_Ev` INT NOT NULL,
  `iduser` INT NOT NULL,
  `Nome_Ev` VARCHAR(45) NULL,
  `Descrição` VARCHAR(45) NULL,
  `Duração` VARCHAR(20) NOT NULL,
  `Localização` VARCHAR(25) NOT NULL,
  `Supervisor` VARCHAR(45) NOT NULL,
  `Participantes` VARCHAR(45) NULL,
  `Publico_Alvo` VARCHAR(45) NULL,
  PRIMARY KEY (`id_Ev`));

-- Criando relação entre a tabela eventos e a tabela usuarios
alter table tbeventos
ADD CONSTRAINT FK_CRIA FOREIGN KEY (iduser)  REFERENCES tbusuarios(iduser);

-- Adicionando mais um coluna na tabela

alter table tbeventos
ADD column Data_M TimeStamp;

desc tbeventos;
 
