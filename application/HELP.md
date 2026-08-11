# Read Me First

## Como Configurar a JDK 25?

Para configurar o Java 25 no seu VS Code, você precisa instalar o JDK 25, adicionar a extensão oficial da Microsoft e apontar o caminho do compilador no arquivo settings.json. [1, 2, 3] 
Siga o passo a passo exato para deixar o seu ambiente pronto:

### 1. Instalar o JDK 25

* Baixe e instale o pacote correspondente ao seu sistema operacional diretamente no site da [Oracle Java Downloads](https://www.oracle.com/br/java/technologies/downloads/).
* Importante: Certifique-se de adicionar o JDK às variáveis de ambiente do seu sistema (JAVA_HOME) durante ou após a instalação. [1, 4, 5] 

### 2. Instalar as Extensões no VS Code
Abra a aba de extensões (Ctrl+Shift+X) e instale os seguintes pacotes: [6, 7] 

* Extension Pack for Java (da Microsoft): Habilita o suporte completo ao ecossistema Java.
* Spring Boot Extension Pack (da VMware): Facilita a criação e execução de projetos Spring Boot. [2, 6, 8, 9] 

### 3. Configurar o arquivo settings.json
Para garantir que o VS Code use o runtime do Java 25 para compilar seu projeto, você deve configurar as java.jdt.ls.java.home e java.configuration.runtimes. [10, 11] 

   1. Pressione Ctrl+Shift+P para abrir a paleta de comandos.
   2. Digite e selecione: Preferences: Open User Settings (JSON).
   3. Adicione ou adapte as linhas abaixo dentro das chaves principais (substituindo o caminho pelo local onde o seu JDK 25 foi instalado): [3, 12] 

{
    "java.jdt.ls.java.home": "C:\\Program Files\\Java\\jdk-25",
    "java.configuration.runtimes": [
        {
            "name": "JavaSE-25",
            "path": "C:\\Program Files\\Java\\jdk-25",
            "default": true
        }
    ]
}

(Nota: Se estiver no Mac ou Linux, mude o caminho path para o padrão do seu sistema, como /Library/Java/JavaVirtualMachines/jdk-25.jdk/Contents/Home no macOS).


[1] [https://www.oracle.com](https://www.oracle.com/br/java/technologies/downloads/)
[2] [https://code.visualstudio.com](https://translate.google.com/translate?u=https://code.visualstudio.com/docs/java/java-spring-boot&hl=pt&sl=en&tl=pt&client=sge)
[3] [https://www.youtube.com](https://www.youtube.com/watch?v=rzDHx0gxkNQ&t=525)
[4] [https://cursos.alura.com.br](https://cursos.alura.com.br/forum/topico-duvida-como-posso-fazer-a-build-no-vscode-355777)
[5] [https://www.vivaolinux.com.br](https://www.vivaolinux.com.br/dica/Configurando-ambiente-Java-no-sistema-operacional-Linux/)
[6] [https://medium.com](https://translate.google.com/translate?u=https://medium.com/@alexandre.therrien3/java-spring-tutorial-the-only-tutorial-you-will-need-to-get-started-vs-code-13413e661db5&hl=pt&sl=en&tl=pt&client=sge)
[7] [https://medium.com](https://medium.com/@habbema/java-instala%C3%A7%C3%A3o-0d7109004d13)
[8] [https://www.dio.me](https://www.dio.me/articles/ambiente-de-desenvolvimento-java-e-springboot-com-vscode)
[9] [https://imasters.com.br](https://imasters.com.br/java/visual-studio-code-para-java-o-guia-completo-dicas-configuracao-e-extensoes)
[10] [https://www.youtube.com](https://www.youtube.com/watch?v=TbExD_SzWdA)
[11] [https://www.baeldung.com](https://www.baeldung.com/java-25-features)
[12] [https://prog.academiafa.edu.pt](https://prog.academiafa.edu.pt/exercises/instalar_compilador_vscode_2.htm)
[13] [https://www.youtube.com](https://www.youtube.com/watch?v=dIWHLpxIblk)
[14] [https://www.dio.me](https://www.dio.me/articles/springboot-como-usar-no-vscode-intelij-community-e-eclipse-97d5b0a539c7)


# Getting Started

### Reference Documentation
For further reference, please consider the following sections:

* [Official Apache Maven documentation](https://maven.apache.org/guides/index.html)
* [Spring Boot Maven Plugin Reference Guide](https://docs.spring.io/spring-boot/4.1.0/maven-plugin)
* [Create an OCI image](https://docs.spring.io/spring-boot/4.1.0/maven-plugin/build-image.html)
* [Spring Boot DevTools](https://docs.spring.io/spring-boot/4.1.0/reference/using/devtools.html)
* [Spring Web](https://docs.spring.io/spring-boot/4.1.0/reference/web/servlet.html)
* [Spring Data JPA](https://docs.spring.io/spring-boot/4.1.0/reference/data/sql.html#data.sql.jpa-and-spring-data)
* [Spring Security](https://docs.spring.io/spring-boot/4.1.0/reference/web/spring-security.html)

### Guides
The following guides illustrate how to use some features concretely:

* [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)
* [Serving Web Content with Spring MVC](https://spring.io/guides/gs/serving-web-content/)
* [Building REST services with Spring](https://spring.io/guides/tutorials/rest/)
* [Accessing Data with JPA](https://spring.io/guides/gs/accessing-data-jpa/)
* [Accessing data with MySQL](https://spring.io/guides/gs/accessing-data-mysql/)
* [Securing a Web Application](https://spring.io/guides/gs/securing-web/)
* [Spring Boot and OAuth2](https://spring.io/guides/tutorials/spring-boot-oauth2/)
* [Authenticating a User with LDAP](https://spring.io/guides/gs/authenticating-ldap/)

### Maven Parent overrides

Due to Maven's design, elements are inherited from the parent POM to the project POM.
While most of the inheritance is fine, it also inherits unwanted elements like `<license>` and `<developers>` from the parent.
To prevent this, the project POM contains empty overrides for these elements.
If you manually switch to a different parent and actually want the inheritance, you need to remove those overrides.

