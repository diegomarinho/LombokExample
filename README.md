# LombokExample

podemos reduzir o nosso trabalho usando a biblioteca Projeto Lombok. Que não faz a necessidade de termos que criar getter, setters, hashcode, equals e toString, com o uso de anotações deixa transparente não mostrando o código para o desenvolvedor.

Para seu uso precisamos ter uma IDE instalada para facilitar ainda mais nosso trabalho, nesse exemplo irei usar o Eclipse, vou assumir que você já tem instalado e o ambiente java está configurado, com suas variáveis de ambiente configuradas.

Primeiro passo é fazer o download do projeto nesse link.
Segundo passo é instalar, executando o lombok.jar. Por preferência use via linha de comando para caso de algum erro ocorra você consiga identificar. Como exemplo abaixo:

1
java -jar lombok.jar
Vai ser aberto uma janela para que seja escolhido quais IDEs será instalado o plugin, escolhendo clique em Install / Update.
Após a instalação ser concluída caso seu Eclipse esteja aberto feche e abra novamente para que as alterações tenham efeito.

Pronto temos todo o ambiente funcionando, vamos começar a colocar mão no código.

Para fazer o exemplo irei usar um projeto Maven:
Vou assumir que vocês sabem criar um projeto novo com o uso do Maven.
Vamos adicionar a dependência e o repositório dentro do projeto, então abra o arquivo pom.xml do seu projeto e insira:

# Dependência:

```xml
<!-- LOMBOK-->
<dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <version>0.12.0</version>
</dependency>

```
# Repositório:

```xml
<!-- REPOSITORIOS -->
<repositories>
    <!-- LOMBOK -->
    <repository>
        <id>projectlombok.org</id>
        <url>http://projectlombok.org/mavenrepo</url>
    </repository>
</repositories>

```
Com o projeto já configurado agora podemos colocar mão no código Java.

# Crie uma classe de modelo como abaixo:

```java
import lombok.Data;
 
@Data
public class Usuario {
    private String usuario;
    private String senha;
}

```
# Vamos testar com o código abaixo:

```java
public class App 
{
    public static void main( String[] args )
    {
        Usuario usuario = new Usuario();
        usuario.setUsuario("Revton");
        usuario.setSenha("r13245");
        System.out.println(usuario);
    }
}

```
# Execute e verifique que a saida ao executar o System.out.println(usuario) é essa:

```java
Usuario(usuario=Revton, senha=r13245)

```
Pronto seu exemplo concluído, podemos perceber a facilidade de usar essa biblioteca deixando o código mais limpo, espero que tenha ajudado a ver as vantagens de usar esse projeto que vem para facilitar nosso trabalho.
