# https-github.com-LDIANE-arara-turismo-back
@@ -0,0 +1,33 @@
HELP.md
alvo /
! .mvn / wrapper / maven-wrapper.jar
! ** / src / principal / ** / destino /
! ** / src / teste / ** / destino /

# ## STS ###
.apt_generated
.classpath
.factorypath
.projeto
.definições
.springBeans
.sts4-cache

# ## IDEIA do IntelliJ ###
.ideia
* .iws
* .iml
* .ipr

# ## NetBeans ###
/ nbproject / privado /
/ nbbuild /
/ distância /
/ nbdist /
/ .nb-gradle /
construir /
! ** / src / main / ** / build /
! ** / src / teste / ** / construir /

# ## Código VS ###
.vscode /
 BIN +57,4 KB .mvn/wrapper/maven-wrapper.jar 
Arquivo binário não mostrado.
 2 .mvn/wrapper/maven-wrapper.properties 
@@ -0,0 +1,2 @@
DistributionUrl =https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.8.4/apache-maven-3.8.4-bin.zip
wrapperUrl = https://repo.maven.apache.org/maven2/org/apache/maven/wrapper/maven-wrapper/3.1.0/maven-wrapper-3.1.0.jar
 316 mvnw 
@@ -0,0 +1,316 @@
#! /bin/sh
# ------------------------------------------------- ---------------------------
# Licenciado para a Apache Software Foundation (ASF) sob um
# ou mais contratos de licença de contribuidor. Veja o arquivo AVISO
# distribuído com este trabalho para informações adicionais
# sobre propriedade de direitos autorais. A ASF licencia este arquivo
# para você sob a Licença Apache, Versão 2.0 (o
# "Licença"); você não pode usar este arquivo, exceto em conformidade
# com a Licença. Você pode obter uma cópia da Licença em
#
#     https://www.apache.org/licenses/LICENSE-2.0
#
# A menos que exigido pela lei aplicável ou acordado por escrito,
# software distribuído sob a Licença é distribuído em um
# BASE "COMO ESTÁ", SEM GARANTIAS OU CONDIÇÕES DE QUALQUER
# KIND, seja expresso ou implícito. Consulte a Licença para o
# idioma específico que rege as permissões e limitações
# sob a Licença.
# ------------------------------------------------- ---------------------------

# ------------------------------------------------- ---------------------------
# Maven Start Up Batch script
#
# Variáveis ​​ENV necessárias:
# ------------------
#    JAVA_HOME - localização de um diretório inicial do JDK
#
# Variáveis ​​ENV opcionais
# -----------------
#    M2_HOME - localização do diretório inicial instalado do maven2
#    MAVEN_OPTS - parâmetros passados ​​para o Java VM ao executar o Maven
#      por exemplo, para depurar o próprio Maven, use
#        set MAVEN_OPTS=-Xdebug -Xrunjdwp:transport=dt_socket,server=y,suspend=y,address=8000
#    MAVEN_SKIP_RC - sinalizador para desabilitar o carregamento de arquivos mavenrc
# ------------------------------------------------- ---------------------------

if [ -z  " $ MAVEN_SKIP_RC " ] ;  então

  if [ -f /usr/local/etc/mavenrc ] ;  então
    . /usr/local/etc/mavenrc
  fi

  if [ -f /etc/mavenrc ] ;  então
    . /etc/mavenrc
  fi

  if [ -f  " $HOME /.mavenrc " ] ;  então
    .  " $HOME /.mavenrc "
  fi

fi

# Suporte específico do SO. $var _must_ ser definido como verdadeiro ou falso.
cygwin=falso ;
darwin=falso ;
mingw=falso
caso  " ` uname ` "  em
  CYGWIN * ) cygwin=true ;;
  MINGW * ) mingw=true;;
  Darwin * ) darwin=true
    # Use /usr/libexec/java_home se disponível, caso contrário, volte para /Library/Java/Home
    # Veja https://developer.apple.com/library/mac/qa/qa1170/_index.html
    if [ -z  " $JAVA_HOME " ] ;  então
      if [ -x  " /usr/libexec/java_home " ] ;  então
        export JAVA_HOME= " ` /usr/libexec/java_home ` "
      outro
        export JAVA_HOME= " /Biblioteca/Java/Home "
      fi
    fi
    ;;
esac

if [ -z  " $JAVA_HOME " ] ;  então
  if [ -r /etc/gentoo-release ] ;  então
    JAVA_HOME= ` java-config --jre-home `
  fi
fi

if [ -z  " $M2_HOME " ] ;  então
  # # resolve links - $0 pode ser um link para a página inicial do maven
  PRG= " $0 "

  # precisa disso para links simbólicos relativos
  while [ -h  " $PRG " ] ;  Faz
    ls= ` ls -ld " $PRG " `
    link= ` expr " $ls "  :  ' .*-> \(.*\)$ ' `
    if expr " $link "  :  ' /.* '  > /dev/null ;  então
      PRG= " $link "
    outro
      PRG= " ` dirname " $PRG " ` / $ link "
    fi
  feito

salvodir   = ` pwd`

  M2_HOME= ` dirname " $PRG " ` /..

  # torná-lo totalmente qualificado
  M2_HOME= ` cd " $M2_HOME "  && pwd `

  cd  " $saveddir "
  # echo Usando m2 em $M2_HOME
fi

# Para Cygwin, certifique-se de que os caminhos estejam no formato UNIX antes que qualquer coisa seja tocada
if  $cygwin  ;  então
  [ -n  " ​​$M2_HOME " ] &&
    M2_HOME= ` cygpath --unix " $M2_HOME " `
  [ -n  " ​​$JAVA_HOME " ] &&
    JAVA_HOME= ` cygpath --unix " $JAVA_HOME " `
  [ -n  " ​​$CLASSPATH " ] &&
    CLASSPATH= ` cygpath --path --unix " $CLASSPATH " `
fi

# Para Mingw, certifique-se de que os caminhos estejam no formato UNIX antes que qualquer coisa seja tocada
if  $mingw  ;  então
  [ -n  " ​​$M2_HOME " ] &&
    M2_HOME= " ` (cd " $M2_HOME " ; pwd) ` "
  [ -n  " ​​$JAVA_HOME " ] &&
    JAVA_HOME= " ` (cd " $JAVA_HOME " ; pwd) ` "
fi

if [ -z  " $JAVA_HOME " ] ;  então
  javaExecutable= " ` which javac ` "
  if [ -n  " ​​$javaExecutable " ] &&  ! [ " ` expr \" $javaExecutable \"  :  ' \([^ ]*\) ' ` "  =  " no " ] ;  então
    # readlink(1) não está disponível como padrão no Solaris 10.
    readLink= ` which readlink `
    se [ !  ` expr " $readLink "  :  ' \([^ ]*\) ' `  =  " no " ] ;  então
      if  $darwin  ;  então
        javaHome= " ` dirname \" $javaExecutable \" ` "
        javaExecutable= " ` cd \" $javaHome \"  &&  pwd -P ` /javac "
      outro
        javaExecutable= " ` readlink -f \" $javaExecutable \" ` "
      fi
      javaHome= " ` dirname \" $javaExecutable \" ` "
      javaHome= ` expr " $javaHome "  :  ' \(.*\)/bin ' `
      JAVA_HOME= " $javaHome "
      exportar JAVA_HOME
    fi
  fi
fi

if [ -z  " $JAVACMD " ] ;  então
  if [ -n  " ​​$JAVA_HOME "   ] ;  então
    if [ -x  " $JAVA_HOME /jre/sh/java " ] ;  então
      # O JDK da IBM no AIX usa locais estranhos para os executáveis
      JAVACMD= " $JAVA_HOME /jre/sh/java "
    outro
      JAVACMD= " $JAVA_HOME /bin/java "
    fi
  outro
    JAVACMD= " ` \\ unset -f command ;  \\ command -v java ` "
  fi
fi

se [ !  -x  " $JAVACMD " ] ;  então
  echo  " Erro: JAVA_HOME não está definido corretamente. "  >&2
  echo  "   Não podemos executar $JAVACMD "  >&2
  saída 1
fi

if [ -z  " $JAVA_HOME " ] ;  então
  echo  " Aviso: a variável de ambiente JAVA_HOME não está definida. "
fi

CLASSWORLDS_LAUNCHER=org.codehaus.plexus.classworlds.launcher.Launcher

# percorre a estrutura de diretórios do diretório de trabalho do processo para a raiz do sistema de arquivos
# o primeiro diretório com o subdiretório .mvn é considerado o diretório base do projeto
find_maven_basedir () {

  if [ -z  " $ 1 " ]
  então
    echo  " Caminho não especificado para find_maven_basedir "
    retornar 1
  fi

  basedir= " $1 "
  wdir= " $1 "
  while [ " $ wdir "  !=  ' / ' ] ;  Faz
    if [ -d  " $wdir " /.mvn ] ;  então
      basedir= $wdir
      pausa
    fi
    # solução alternativa para JBEAP-8937 (no Solaris 10/Sparc)
    if [ -d  " ${wdir} " ] ;  então
      wdir= ` cd " $wdir /.. " ; pwd `
    fi
    # fim da solução alternativa
  feito
  echo  " ${basedir} "
}

# concatena todas as linhas de um arquivo
concat_lines () {
  if [ -f  " $ 1 " ] ;  então
    echo  " $( tr -s ' \n '  '  '  <  " $ 1 " ) "
  fi
}

BASE_DIR= ` find_maven_basedir " $( pwd ) " `
if [ -z  " $ BASE_DIR " ] ;  então
  saída 1 ;
fi

################################################# _ #######################################
# Extensão para permitir o download automático do maven-wrapper.jar do Maven-central
# Isso permite usar o wrapper maven em projetos que proíbem a verificação de dados binários.
################################################# _ #######################################
if [ -r  " $BASE_DIR /.mvn/wrapper/maven-wrapper.jar " ] ;  então
    if [ " $MVNW_VERBOSE "  =  true ] ;  então
      echo  " Encontrado .mvn/wrapper/maven-wrapper.jar "
    fi
outro
    if [ " $MVNW_VERBOSE "  =  true ] ;  então
      echo  " Não foi possível encontrar .mvn/wrapper/maven-wrapper.jar, baixando ... "
    fi
    if [ -n  " ​​$MVNW_REPOURL " ] ;  então
      jarUrl= " $MVNW_REPOURL /org/apache/maven/wrapper/maven-wrapper/3.1.0/maven-wrapper-3.1.0.jar "
    outro
      jarUrl= " https://repo.maven.apache.org/maven2/org/apache/maven/wrapper/maven-wrapper/3.1.0/maven-wrapper-3.1.0.jar "
    fi
    while IFS= " = "  lê o valor da chave ;  Faz
      case  " $chave "  in (wrapperUrl) jarUrl= " $valor " ;  quebrar ;;
      esac
    feito  <  " $BASE_DIR /.mvn/wrapper/maven-wrapper.properties "
    if [ " $MVNW_VERBOSE "  =  true ] ;  então
      echo  " Baixando de: $jarUrl "
    fi
    wrapperJarPath= " $BASE_DIR /.mvn/wrapper/maven-wrapper.jar "
    if  $cygwin ;  então
      wrapperJarPath= ` cygpath --path --windows " $wrapperJarPath " `
    fi

    if  comando -v wget > /dev/null ;  então
        if [ " $MVNW_VERBOSE "  =  true ] ;  então
          echo  " Encontrou wget ... usando wget "
        fi
        if [ -z  " $MVNW_USERNAME " ] || [ -z  " $MVNW_PASSWORD " ] ;  então
            wget " $jarUrl " -O " $wrapperJarPath "  || rm -f " $wrapperJarPath "
        outro
            wget --http-user= $MVNW_USERNAME --http-password= $MVNW_PASSWORD  " $jarUrl " -O " $wrapperJarPath "  || rm -f " $wrapperJarPath "
        fi
     comando elif -v curl > /dev/null ;  então
        if [ " $MVNW_VERBOSE "  =  true ] ;  então
          echo  " Encontrado curl ... usando curl "
        fi
        if [ -z  " $MVNW_USERNAME " ] || [ -z  " $MVNW_PASSWORD " ] ;  então
            curl -o " $wrapperJarPath "  " $ jarUrl " -f
        outro
            curl --user $MVNW_USERNAME : $MVNW_PASSWORD -o " $wrapperJarPath "  " $ jarUrl " -f
        fi

    outro
        if [ " $MVNW_VERBOSE "  =  true ] ;  então
          echo  " Voltando a usar Java para fazer download "
        fi
        javaClass= " $BASE_DIR /.mvn/wrapper/MavenWrapperDownloader.java "
        # Para Cygwin, mude os caminhos para o formato Windows antes de executar o javac
        if  $cygwin ;  então
          javaClass= ` cygpath --path --windows " $javaClass " `
        fi
        if [ -e  " $javaClass " ] ;  então
            se [ !  -e  " $BASE_DIR /.mvn/wrapper/MavenWrapperDownloader.class " ] ;  então
                if [ " $MVNW_VERBOSE "  =  true ] ;  então
                  echo  " - Compilando MavenWrapperDownloader.java ... "
                fi
                # Compilando a classe Java
                ( " $JAVA_HOME /bin/javac "  " $ javaClass " )
            fi
            if [ -e  " $BASE_DIR /.mvn/wrapper/MavenWrapperDownloader.class " ] ;  então
                # Executando o download
                if [ " $MVNW_VERBOSE "  =  true ] ;  então
                  echo  " - Executando MavenWrapperDownloader.java ... "
                fi
                ( " $JAVA_HOME /bin/java " -cp .mvn/wrapper MavenWrapperDownloader " $ MAVEN_PROJECTBASEDIR " )
            fi
        fi
    fi
fi
################################################# _ #######################################
# Fim da extensão
################################################# _ #######################################

export MAVEN_PROJECTBASEDIR= ${MAVEN_BASEDIR :- " $BASE_DIR " }
if [ " $MVNW_VERBOSE "  =  true ] ;  então
  echo  $MAVEN_PROJECTBASEDIR
fi
MAVEN_OPTS= " $( concat_lines " $ MAVEN_PROJECTBASEDIR /.mvn/jvm.config " )  $ MAVEN_OPTS "

# Para Cygwin, mude os caminhos para o formato Windows antes de executar o java
if  $cygwin ;  então
  [ -n  " ​​$M2_HOME " ] &&
    M2_HOME= ` cygpath --path --windows " $M2_HOME " `
  [ -n  " ​​$JAVA_HOME " ] &&
    JAVA_HOME= ` cygpath --path --windows " $JAVA_HOME " `
  [ -n  " ​​$CLASSPATH " ] &&
    CLASSPATH= ` cygpath --path --windows " $CLASSPATH " `
  [ -n  " ​​$MAVEN_PROJECTBASEDIR " ] &&
    MAVEN_PROJECTBASEDIR= ` cygpath --path --windows " $MAVEN_PROJECTBASEDIR " `
fi

# Forneça uma maneira "padronizada" de recuperar os argumentos da CLI que
# trabalhe com execuções Windows e não Windows.
MAVEN_CMD_LINE_ARGS= " $MAVEN_CONFIG  $@ "
exportar MAVEN_CMD_LINE_ARGS

WRAPPER_LAUNCHER=org.apache.maven.wrapper.MavenWrapperMain

exec  " $JAVACMD " \
  $MAVEN_OPTS \
  $MAVEN_DEBUG_OPTS \
  -classpath " $MAVEN_PROJECTBASEDIR /.mvn/wrapper/maven-wrapper.jar " \
  " -Dmaven.home= ${M2_HOME} " \
  " -Dmaven.multiModuleProjectDirectory= ${MAVEN_PROJECTBASEDIR} " \
  ${WRAPPER_LAUNCHER}  $MAVEN_CONFIG  " $@ "
 188 mvnw.cmd 
@@ -0,0 +1,188 @@
@REM ------------------------------------------------ _ ----------------------------
@ REM Licenciado para a Apache Software Foundation (ASF) sob um
@ REM ou mais contratos de licença de contribuidor. Veja o arquivo AVISO
@ REM distribuído com este trabalho para informações adicionais
@ REM sobre propriedade de direitos autorais. A ASF licencia este arquivo
@ REM para você sob a Licença Apache, Versão 2.0 (o
@REM " Licença "); você não pode usar este arquivo, exceto em conformidade
@ REM com a Licença. Você pode obter uma cópia da Licença em
@REM _
@REM     https://www.apache.org/licenses/LICENSE-2.0 _
@REM _
@ REM A menos que exigido pela lei aplicável ou acordado por escrito,
@ O software REM distribuído sob a Licença é distribuído em um
@ REM BASE "COMO ESTÁ", SEM GARANTIAS OU CONDIÇÕES DE QUALQUER
@ REM KIND, expressa ou implícita. Consulte a Licença para o
@ Linguagem específica do REM que rege as permissões e limitações
@ REM sob a Licença.
@REM ------------------------------------------------ _ ----------------------------

@REM ------------------------------------------------ _ ----------------------------
@ REM Maven Start Up Batch script
@REM _
@ REM Vars ENV necessárias:
@ REM JAVA_HOME - localização de um diretório inicial do JDK
@REM _
@ REM Opcional ENV vars
@ REM M2_HOME - localização do diretório inicial instalado do maven2
@ REM MAVEN_BATCH_ECHO - definido como 'on' para habilitar o eco dos comandos em lote
@ REM MAVEN_BATCH_PAUSE - definido como 'on' para aguardar um pressionamento de tecla antes de terminar
@ REM MAVEN_OPTS - parâmetros passados ​​para o Java VM ao executar o Maven
@ REM      , por exemplo, para depurar o próprio Maven, use
@ REM set MAVEN_OPTS=-Xdebug -Xrunjdwp:transport=dt_socket,server=y,suspend=y,address=8000
@ REM MAVEN_SKIP_RC - sinalizador para desabilitar o carregamento de arquivos mavenrc
@REM ------------------------------------------------ _ ----------------------------

@ REM Inicia todas as linhas REM com '@' caso MAVEN_BATCH_ECHO esteja 'on'
@ eco  desligado
@ REM define o título da janela de comando
título  %0
@ REM habilita o eco configurando MAVEN_BATCH_ECHO para 'on'
@ if " %MAVEN_BATCH_ECHO% "  ==  " em "   echo  %MAVEN_BATCH_ECHO%

@ REM defina %HOME% para o equivalente a $HOME
if  " %HOME% "  ==  " " (definir " HOME = %HOMEDRIVE%%HOMEPATH% " )

@ REM Executa um script definido pelo usuário antes deste
se  não  " %MAVEN_SKIP_RC% "  ==  " "  vá para pularRcPre
@ REM verifica o pré-script, uma vez com o final .bat legado e uma vez com final .cmd
se  existir  " %USERPROFILE% \mavenrc_pre.bat "  chame  " %USERPROFILE% \mavenrc_pre.bat "  %*
se  existir  " %USERPROFILE% \mavenrc_pre.cmd "  chame  " %USERPROFILE% \mavenrc_pre.cmd "  %*
: skipRcPre

@setlocal _

definir  ERROR_CODE = 0

@ REM Para isolar variáveis ​​internas de possíveis pós scripts, usamos outro setlocal
@setlocal _

@ REM ==== INICIAR VALIDAÇÃO ====
se  não  " %JAVA_HOME% "  ==  " "  vá para OkJHome

eco .
echo Erro: JAVA_HOME não encontrado em seu ambiente. >& 2
echo Por favor, defina a variável JAVA_HOME em seu ambiente para corresponder ao >& 2
echo localização de sua instalação Java. >& 2
eco .
erro goto

: OkJHome
se  existir  " %JAVA_HOME% \bin\java.exe "  vá para init

eco .
echo Erro: JAVA_HOME está configurado para um diretório inválido. >& 2
echo JAVA_HOME = " %JAVA_HOME% "  >& 2
echo Por favor, defina a variável JAVA_HOME em seu ambiente para corresponder ao >& 2
echo localização de sua instalação Java. >& 2
eco .
erro goto

@REM ==== FIM DA VALIDAÇÃO ====

: inicializar

@ REM Localize o diretório base do projeto, ou seja, o diretório que contém a pasta ".mvn".
@ REM Fallback para o diretório de trabalho atual se não for encontrado.

definir  MAVEN_PROJECTBASEDIR = %MAVEN_BASEDIR%
SE  NÃO  " %MAVEN_PROJECTBASEDIR% " == " "  vá para endDetectBaseDir

definir  EXEC_DIR = %CD%
definir  WDIR = %EXEC_DIR%
: findBaseDir
IF  EXIST  " %WDIR% " \.mvn vai para baseDirFound
cd ..
IF  " %WDIR% " == " %CD% "  vai para baseDirNotFound
definir  WDIR = %CD%
vá para encontrarBaseDir

: baseDirFound
definir  MAVEN_PROJECTBASEDIR = %WDIR%
cd  " %EXEC_DIR% "
goto endDetectBaseDir

: baseDirNotFound
definir  MAVEN_PROJECTBASEDIR = %EXEC_DIR%
cd  " %EXEC_DIR% "

: endDetectBaseDir

SE  NÃO  EXISTE  " %MAVEN_PROJECTBASEDIR% \.mvn\jvm.config "  vá para endReadAdditionalConfig

@ setlocal EnableExtensions EnableDelayedExpansion
para /F " usebackq delims= "  %%a  em ( " %MAVEN_PROJECTBASEDIR% \.mvn\jvm.config " ) defina JVM_CONFIG_MAVEN_PROPS  = ! JVM_CONFIG_MAVEN_PROPS ! %%uma  
@ endlocal  &  set  JVM_CONFIG_MAVEN_PROPS = %JVM_CONFIG_MAVEN_PROPS%

: endReadAdditionalConfig

SET  MAVEN_JAVA_EXE = " %JAVA_HOME% \bin\java.exe "
set  WRAPPER_JAR = " %MAVEN_PROJECTBASEDIR% \.mvn\wrapper\maven-wrapper.jar "
set  WRAPPER_LAUNCHER = org.apache.maven.wrapper.MavenWrapperMain

set  DOWNLOAD_URL = " https://repo.maven.apache.org/maven2/org/apache/maven/wrapper/maven-wrapper/3.1.0/maven-wrapper-3.1.0.jar "

FOR /F " usebackq tokens=1,2 delims== "  %%A  IN ( " %MAVEN_PROJECTBASEDIR% \.mvn\wrapper\maven-wrapper.properties " ) DO (
    IF  " %%A " == " wrapperUrl "  SET  DOWNLOAD_URL = %%B
)

@ REM Extension para permitir o download automático do maven-wrapper.jar do Maven-central
@ REM Isso permite usar o wrapper maven em projetos que proíbem a verificação de dados binários.
se  existir  %WRAPPER_JAR% (
    if  " %MVNW_VERBOSE% "  ==  " true " (
        echo encontrado %WRAPPER_JAR%
    )
) outro (
    se  não  " %MVNW_REPOURL% "  ==  " " (
        SET  DOWNLOAD_URL = " %MVNW_REPOURL% /org/apache/maven/wrapper/maven-wrapper/3.1.0/maven-wrapper-3.1.0.jar "
    )
    if  " %MVNW_VERBOSE% "  ==  " true " (
        echo Não foi possível encontrar %WRAPPER_JAR% , baixando...
        echo Baixando de: %DOWNLOAD_URL%
    )

    powershell -Comando " &{ " ^
		" $webclient = novo objeto System.Net.WebClient; " ^
		" if (-not ([string]::IsNullOrEmpty(' %MVNW_USERNAME% ') -and [string]::IsNullOrEmpty(' %MVNW_PASSWORD% '))) { " ^
		" $webclient.Credentials = new-object System.Net.NetworkCredential(' %MVNW_USERNAME% ', ' %MVNW_PASSWORD% '); " ^
		" } " ^
		" [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; $webclient.DownloadFile(' %DOWNLOAD_URL% ', ' %WRAPPER_JAR% ') " ^
		" } "
    if  " %MVNW_VERBOSE% "  ==  " true " (
        echo Download concluído de %WRAPPER_JAR%
    )
)
@ REM Fim da extensão

@ REM Fornece uma maneira "padronizada" de recuperar os argumentos CLI que
@ REM funcionam com execuções Windows e não Windows.
definir  MAVEN_CMD_LINE_ARGS = %*

%MAVEN_JAVA_EXE%  ^
  %JVM_CONFIG_MAVEN_PROPS%  ^
  %MAVEN_OPTS%  ^
  %MAVEN_DEBUG_OPTS%  ^
  -caminho de classe %WRAPPER_JAR%  ^
  " -Dmaven.multiModuleProjectDirectory= %MAVEN_PROJECTBASEDIR% "  ^
  %WRAPPER_LAUNCHER%  %MAVEN_CONFIG%  %*
se  ERRORLEVEL  1  tem erro
tem que terminar

: erro
definir  ERROR_CODE = 1

: fim
@ endlocal  &  set  ERROR_CODE = %ERROR_CODE%

se  não  " %MAVEN_SKIP_RC% " == " "  vá para pularRcPost
@ REM verifica o post script, uma vez com o final .bat legado e uma vez com final .cmd
se  existir  " %USERPROFILE% \mavenrc_post.bat "  chame  " %USERPROFILE% \mavenrc_post.bat "
se  existir  " %USERPROFILE% \mavenrc_post.cmd "  chame  " %USERPROFILE% \mavenrc_post.cmd "
: skipRcPost

@ REM pausa o script se MAVEN_BATCH_PAUSE estiver definido como 'on'
if  " %MAVEN_BATCH_PAUSE% " == " em "  pausa

if  " %MAVEN_TERMINATE_CMD% " == " em "  saia  %ERROR_CODE%

cmd /C exit /B %ERROR_CODE%
 67 pom.xml 
@@ -0,0 +1,67 @@
<? xml version = " 1.0 " encoding = " UTF-8 " ?>
< projeto  xmlns = " http://maven.apache.org/POM/4.0.0 "  xmlns : xsi = " http://www.w3.org/2001/XMLSchema-instance "
	xsi:schemaLocation= " http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd " >
	< modelVersion >4.0.0</ modelVersion >
	< pai >
		< groupId >org.springframework.boot</ groupId >
		< artefatoId >spring-boot-starter-parent</ artefatoId >
		< versão >2.6.4</ versão >
		< relativPath /> <!-- pesquisa pai do repositório -->
	</ pai >
	< groupId >com.arara</ groupId >
	< artefatoId >arara-turismo</ artefatoId >
	< versão >0.0.1-INSTANTÂNEO</ versão >
	< name >arara-turismo</ name >
	< description >Projeto de demonstração para Spring Boot</ descrição >
	< propriedades >
		< java .version>17</ java .version>
	</ propriedades >
	< dependências >
		< dependência >
			< groupId >org.springframework.boot</ groupId >
			< artefatoId >spring-boot-starter-data-jpa</ artefatoId >
		</ dependência >
		< dependência >
			< groupId >org.springframework.boot</ groupId >
			< artefatoId >spring-boot-starter-security</ artefatoId >
		</ dependência >
		< dependência >
			< groupId >org.springframework.boot</ groupId >
			< artifactId >spring-boot-starter-validation</ artifactId >
		</ dependência >
		< dependência >
			< groupId >org.springframework.boot</ groupId >
			< artefatoId >spring-boot-starter-web</ artefatoId >
		</ dependência >
		< dependência >
			< groupId >io.jsonwebtoken</ groupId >
			< artefatoId >jjwt</ artefatoId >
			< versão >0.9.1</ versão >
		</ dependência >
		< dependência >
			< groupId >mysql</ groupId >
			< artefatoId >mysql-connector-java</ artefatoId >
			< escopo >tempo de execução</ escopo >
		</ dependência >
		< dependência >
			< groupId >org.springframework.boot</ groupId >
			< artefatoId >spring-boot-starter-test</ artefatoId >
			< escopo >teste</ escopo >
		</ dependência >
		< dependência >
			< groupId >org.springframework.security</ groupId >
			< artefatoId >spring-security-test</ artifactId >
			< escopo >teste</ escopo >
		</ dependência >
	</ dependências >

	< construir >
		< plugins >
			< plugins >
				< groupId >org.springframework.boot</ groupId >
				< artefatoId >spring-boot-maven-plugin</ artefatoId >
			</ plug -in >
		</ plug- ins >
	</ construir >

</ projeto >
 13 src/main/java/com/arara/araraturismo/AraraTurismoApplication.java 
@@ -0,0 +1,13 @@
pacote  com . Arara . araraturismo ;

importar  org . springframework . inicialização . SpringApplication ;
importar  org . springframework . inicialização . autoconfigurar . Aplicativo SpringBoot ;

@SpringBootApplication _
public  class  AraraTurismoApplication {

	public  static  void  main ( String [] args ) {
		SpringApplication . run ( AraraTurismoApplication.class , args ) ; _
	}

}
 114 src/main/java/com/arara/araraturismo/controllers/AuthController.java 
@@ -0,0 +1,114 @@
pacote  com . Arara . araraturismo . controladores ;

importar  java . útil . HashSet ;
importar  java . útil . Lista ;
importar  java . útil . Definir ;
importar  java . útil . fluxo . Coletores ;
importar  javax . validação . Válido ;

import  com . Arara . araraturismo . modelos . ERole ;
import  com . Arara . araraturismo . modelos . Função ;
import  com . Arara . araraturismo . modelos . Usuário ;
import  com . Arara . araraturismo . carga útil . pedido . Solicitação de Login ;
import  com . Arara . araraturismo . carga útil . pedido . Solicitação de inscrição ;
import  com . Arara . araraturismo . carga útil . resposta . MensagemResposta ;
import  com . Arara . araraturismo . carga útil . resposta . UserInfoResponse ;
import  com . Arara . araraturismo . repositórios . RoleRepository ;
import  com . Arara . araraturismo . repositórios . UserRepository ;
import  com . Arara . araraturismo . segurança . jwt . JwtUtils ;
import  com . Arara . araraturismo . segurança . serviços . UserDetailsImpl ;
importar  org . springframework . feijão . fábrica . anotação . Autowired ;
importar  org . springframework . http . HttpHeaders ;
importar  org . springframework . http . Cookie de Resposta ;
importar  org . springframework . http . ResponseEntidade ;
importar  org . springframework . segurança . autenticação . Gerenciador de Autenticação ;
importar  org . springframework . segurança . autenticação . Nome de usuárioSenhaAuthenticationToken ;
importar  org . springframework . segurança . núcleo . Autenticação ;
importar  org . springframework . segurança . núcleo . contexto . SecurityContextHolder ;
importar  org . springframework . segurança . criptografia . senha . Codificador de Senha ;
importar  org . springframework . web . vincular . anotação . CrossOrigin ;
importar  org . springframework . web . vincular . anotação . Pós-Mapeamento ;
importar  org . springframework . web . vincular . anotação . RequestBody ;
importar  org . springframework . web . vincular . anotação . Mapeamento de Solicitação ;
importar  org . springframework . web . vincular . anotação . RestController ;

@CrossOrigin ( origens = "* " , maxAge = 3600 )
@ RestController
@ RequestMapping ( "/api/auth" )
public  class  AuthController {
    @ Autowired
    AuthenticationManager  authenticationManager ;
    @ Autowired
    UserRepository  userRepository ;
    @ Autowired
    RoleRepository  roleRepository ;
    @ Autowired
     Codificador PasswordEncoder ;
    @ Autowired
    JwtUtils  jwtUtils ;

    @ PostMapping ( "/signin" )
    public  ResponseEntity <?> authenticateUser ( @ Valid  @ RequestBody  LoginRequest  loginRequest ) {
        Autenticação de  autenticação = authenticationManager
                . autenticar ( new  UsernamePasswordAuthenticationToken ( loginRequest . getUsername (), loginRequest . getPassword ()));
        SecurityContextHolder . getContext (). setAuthentication ( autenticação );
        UserDetailsImpl  userDetails = ( UserDetailsImpl ) autenticação . getPrincipal ();
        ResponseCookie  jwtCookie = jwtUtils . gerarJwtCookie ( userDetails );
        List < String > roles = userDetails . getAutoridades (). fluxo ()
                . map ( item -> item . getAuthority ())
                . collect ( Collectors . toList ());
        retorne  ResponseEntity . tudo bem (). cabeçalho ( HttpHeaders . SET_COOKIE , jwtCookie . toString ())
                . body ( new  UserInfoResponse ( userDetails . getId (),
                        userDetails . getUsuário (),
                        userDetails . getEmail (),
                        papéis ));
    }
    @ PostMapping ( "/signup" )
    public  ResponseEntity <?> registerUser ( @ Valid  @ RequestBody  SignupRequest  signUpRequest ) {
        if ( userRepository . existByUsername ( signUpRequest . getUsername ())) {
            retorne  ResponseEntity . badRequest (). body ( new  MessageResponse ( "Erro: o nome de usuário já foi usado!" ));
        }
        if ( userRepository . existByEmail ( signUpRequest . getEmail ())) {
            retorne  ResponseEntity . badRequest (). body ( new  MessageResponse ( "Erro: Email já está em uso!" ));
        }
        //Cria uma nova conta de usuário
        Usuário  usuário = novo  usuário ( signUpRequest . getUsername (),
                signUpRequest . getEmail (),
                codificador . codificar ( signUpRequest . getPassword ()));
        Defina < String > strRoles = signUpRequest . getRole ();
        Set < Role > roles = new  HashSet <>();
        if ( strRoles == null ) {
            Função  userRole = roleRepository . findByName ( ERole . ROLE_USER )
                    . orElseThrow (() -> new  RuntimeException ( "Erro: Função não encontrada." ));
            papéis . adicionar ( userRole );
        } senão {
            strRoles . forEach ( papel -> {
                alternar ( função ) {
                    caso  "admin" :
                        Função  adminRole = roleRepository . findByName ( ERole . ROLE_ADMIN )
                                . orElseThrow (() -> new  RuntimeException ( "Erro: Função não encontrada." ));
                        papéis . adicionar ( adminRole );
                        quebrar ;
                    caso  "mod" :
                        Role  modRole = roleRepository . findByName ( ERole . ROLE_MODERATOR )
                                . orElseThrow (() -> new  RuntimeException ( "Erro: Função não encontrada." ));
                        papéis . adicionar ( modRole );
                        quebrar ;
                    padrão :
                        Função  userRole = roleRepository . findByName ( ERole . ROLE_USER )
                                . orElseThrow (() -> new  RuntimeException ( "Erro: Função não encontrada." ));
                        papéis . adicionar ( userRole );
                }
            });
        }
        usuário . setRoles ( papéis );
        userRepository . salvar ( usuário );
        retorne  ResponseEntity . ok ( new  MessageResponse ( "Usuário cadastrado com sucesso!" ));
    }
    @ PostMapping ( "/signout" )
    public  ResponseEntity <?> logoutUser () {
         Cookie ResponseCookie = jwtUtils . getCleanJwtCookie ();
        retorne  ResponseEntity . tudo bem (). cabeçalho ( HttpHeaders . SET_COOKIE , cookie . toString ())
                . body ( new  MessageResponse ( "Você foi desconectado!" ));
    }
} 
 33 src/main/java/com/arara/araraturismo/controllers/TestController.java 
@@ -0,0 +1,33 @@
pacote  com . Arara . araraturismo . controladores ;

importar  org . springframework . segurança . acesso . pré-postar . Pré-autorizar ;
importar  org . springframework . web . vincular . anotação . CrossOrigin ;
importar  org . springframework . web . vincular . anotação . GetMapping ;
importar  org . springframework . web . vincular . anotação . Mapeamento de Solicitação ;
importar  org . springframework . web . vincular . anotação . RestController ;

@CrossOrigin ( origens = "* " , maxAge = 3600 )
@ RestController
@ RequestMapping ( "/api/test" )
 classe  pública TestController {

    @ GetMapping ( "/all" )
    public  String  allAccess () {
        return  "Conteúdo Público". ;
    }
    @ GetMapping ( "/usuário" )
    @ PreAuthorize ( "hasRole('USER') ou hasRole('MODERATOR') ou hasRole('ADMIN')" )
    public  String  userAccess () {
        return  "Conteúdo do Usuário." ;
    }
    @ GetMapping ( "/mod" )
    @ PreAuthorize ( "hasRole('MODERATOR')" )
    public  String  moderatorAccess () {
        return  "Quadro de moderadores." ;
    }
    @ GetMapping ( "/admin" )
    @ PreAuthorize ( "hasRole('ADMIN')" )
    public  String  adminAccess () {
        return  "Conselho Administrativo." ;
    }
} 
 7 src/main/java/com/arara/araraturismo/models/ERole.java 
@@ -0,0 +1,7 @@
pacote  com . Arara . araraturismo . modelos ;

public  enum  ERole {
    ROLE_USER ,
    ROLE_MODERATOR ,
    ROLE_ADMIN
} 
 37 src/main/java/com/arara/araraturismo/models/Role.java 
@@ -0,0 +1,37 @@
pacote  com . Arara . araraturismo . modelos ;

importar  javax . persistência .*;

@ Entidade
@ Table ( nome = "funções" )
 classe  pública Função {
    @ ID
    @GeneratedValue ( estratégia = GenerationType . IDENTITY ) _
     ID inteiro  privado ;
    @ Enumerated ( EnumType . STRING )
    @ Coluna ( comprimento = 20 )
     nome ERole  privado ;

     Função pública () {
    }

     função pública ( nome ERole  ) {
        isso . nome = nome ;
    }

    public  Integer  getId () {
         ID de retorno ;
    }

    public  void  setId ( Integer  id ) {
        isso . id = id ;
    }

    public  ERole getNome  ( ) {
         nome de retorno ;
    }

    public  void  setName ( nome ERole  ) {
        isso . nome = nome ;
    }
} 
 86 src/main/java/com/arara/araraturismo/models/User.java 
@@ -0,0 +1,86 @@
pacote  com . Arara . araraturismo . modelos ;

importar  java . útil . HashSet ;
importar  java . útil . Definir ;
importar  javax . persistência .*;
importar  javax . validação . restrições . E- mail ;
importar  javax . validação . restrições . Não Em Branco ;
importar  javax . validação . restrições . Tamanho ;

@ Entidade
@ Table ( nome = "usuários" ,
        restrições únicas = {
                @ UniqueConstraint ( columnNames = "username" ),
                @ UniqueConstraint ( columnNames = "email" )
        })
 classe  pública Usuário {

    @ ID
    @GeneratedValue ( estratégia = GenerationType . IDENTITY ) _
     ID Longo  privado ;
    @NotBlank _
    @ Tamanho ( máx . = 20 )
    private  String nome de  usuário ;
    @NotBlank _
    @ Tamanho ( máx . = 50 )
    @ E- mail
     e- mail privado String  ;
    @NotBlank _
    @ Tamanho ( máx . = 120 )
     senha privada String  ;

    @ ManyToMany ( fetch = FetchType . LAZY )
    @ JoinTable ( name = "user_roles" ,
            joinColumns = @ JoinColumn ( name = "user_id" ),
            inverseJoinColumns = @ JoinColumn ( name = "role_id" ))
    private  Set < Role > roles = new  HashSet <>();

     usuário público () {
    }

    public  User ( String nome de  usuário , String  email , String  senha ) {
        isso . nome de usuário = nome de usuário ;
        isso . e- mail = e- mail ;
        isso . senha = senha ;
    }

    public  Long  getId () {
         ID de retorno ;
    }

    public  void  setId ( Long  id ) {
        isso . id = id ;
    }

    public  String  getUsername () {
        retornar nome de  usuário ;
    }

    public  void  setUsername ( String  username ) {
        isso . nome de usuário = nome de usuário ;
    }

    public  String  getEmail () {
         e-mail de retorno ;
    }

    public  void  setEmail ( String  email ) {
        isso . e- mail = e- mail ;
    }

    public  String  getPassword () {
        retornar  senha ;
    }

    public  void  setPassword ( senha de string  ) {
        isso . senha = senha ;
    }

    public  Set < Role > getRoles () {
         papéis de retorno ;
    }

    public  void  setRoles ( Set < Role > roles ) {
        isso . papéis = papéis ;
    }
} 
 28 src/main/java/com/arara/araraturismo/payload/request/LoginRequest.java 
@@ -0,0 +1,28 @@
pacote  com . Arara . araraturismo . carga útil . pedido ;

importar  javax . validação . restrições . Não Em Branco ;

 classe  pública Solicitação de login {

    @NotBlank _
    private  String nome de  usuário ;

    @NotBlank _
     senha privada String  ;

    public  String  getUsername () {
        retornar nome de  usuário ;
    }

    public  void  setUsername ( String  username ) {
        isso . nome de usuário = nome de usuário ;
    }

    public  String  getPassword () {
        retornar  senha ;
    }

    public  void  setPassword ( senha de string  ) {
        isso . senha = senha ;
    }
} 
 55 src/main/java/com/arara/araraturismo/payload/request/SignupRequest.java 
@@ -0,0 +1,55 @@
pacote  com . Arara . araraturismo . carga útil . pedido ;

importar  java . útil . Definir ;

importar  javax . validação . restrições .*;

 classe  pública Solicitação de inscrição {

    @NotBlank _
    @ Tamanho ( min = 3 , max = 20 )
    private  String nome de  usuário ;

    @NotBlank _
    @ Tamanho ( máx . = 50 )
    @ E- mail
     e- mail privado String  ;

    private  Set < String > role ;

    @NotBlank _
    @ Tamanho ( min = 6 , max = 40 )
     senha privada String  ;

    public  String  getUsername () {
        retornar nome de  usuário ;
    }

    public  void  setUsername ( String  username ) {
        isso . nome de usuário = nome de usuário ;
    }

    public  String  getEmail () {
         e-mail de retorno ;
    }

    public  void  setEmail ( String  email ) {
        isso . e- mail = e- mail ;
    }

    public  String  getPassword () {
        retornar  senha ;
    }

    public  void  setPassword ( senha de string  ) {
        isso . senha = senha ;
    }

    public  Set < String > getRole () {
        devolva  isso . papel ;
    }

    public  void  setRole ( Set < String > role ) {
        isso . função = função ;
    }
} 
 18 src/main/java/com/arara/araraturismo/payload/response/MessageResponse.java 
@@ -0,0 +1,18 @@
pacote  com . Arara . araraturismo . carga útil . resposta ;

 classe  pública MessageResponse {

     mensagem privada String  ;

    public  MessageResponse ( String  mensagem ) {
        isso . mensagem = mensagem ;
    }

    public  String  getMessage () {
         mensagem de retorno ;
    }

    public  void  setMessage ( String  message ) {
        isso . mensagem = mensagem ;
    }
} 
 45 src/main/java/com/arara/araraturismo/payload/response/UserInfoResponse.java 
@@ -0,0 +1,45 @@
pacote  com . Arara . araraturismo . carga útil . resposta ;

importar  java . útil . Lista ;

public  class  UserInfoResponse {
     ID Longo  privado ;
    private  String nome de  usuário ;
     e- mail privado String  ;
    private  List < String > papéis ;

    public  UserInfoResponse ( Long  id , String  username , String  email , List < String > roles ) {
        isso . id = id ;
        isso . nome de usuário = nome de usuário ;
        isso . e- mail = e- mail ;
        isso . papéis = papéis ;
    }

    public  Long  getId () {
         ID de retorno ;
    }

    public  void  setId ( Long  id ) {
        isso . id = id ;
    }

    public  String  getEmail () {
         e-mail de retorno ;
    }

    public  void  setEmail ( String  email ) {
        isso . e- mail = e- mail ;
    }

    public  String  getUsername () {
        retornar nome de  usuário ;
    }

    public  void  setUsername ( String  username ) {
        isso . nome de usuário = nome de usuário ;
    }

    public  List < String > getRoles () {
         papéis de retorno ;
    }
} 
 13 src/main/java/com/arara/araraturismo/repositories/RoleRepository.java 
@@ -0,0 +1,13 @@
pacote  com . Arara . araraturismo . repositórios ;

importar  java . útil . Opcional ;

import  com . Arara . araraturismo . modelos . ERole ;
import  com . Arara . araraturismo . modelos . Função ;
importar  org . springframework . dados . jpa . repositório . JpaRepository ;
importar  org . springframework . estereótipo . Repositório ;

@ Repositório
 interface  pública RoleRepository  estende  JpaRepository < Role , Long > {
    Opcional < Role > findByName ( ERole  name );
} 
 15 src/main/java/com/arara/araraturismo/repositories/UserRepository.java 
@@ -0,0 +1,15 @@
pacote  com . Arara . araraturismo . repositórios ;

importar  java . útil . Opcional ;

import  com . Arara . araraturismo . modelos . Usuário ;
importar  org . springframework . dados . jpa . repositório . JpaRepository ;
importar  org . springframework . estereótipo . Repositório ;

@ Repositório
 interface  pública UserRepository  estende  JpaRepository < User , Long > {

    Opcional < Usuário > findByUsername ( String nome de  usuário );
    Boolean  existByUsername ( String nome de  usuário );
    Boolean  existByEmail ( String  email );
} 
 58 src/main/java/com/arara/araraturismo/security/WebSecurityConfig.java 
@@ -0,0 +1,58 @@
pacote  com . Arara . araraturismo . segurança ;

import  com . Arara . araraturismo . segurança . jwt . AuthEntryPointJwt ;
import  com . Arara . araraturismo . segurança . jwt . AuthTokenFilter ;
import  com . Arara . araraturismo . segurança . serviços . UserDetailsServiceImpl ;
importar  org . springframework . feijão . fábrica . anotação . Autowired ;
importar  org . springframework . contexto . anotação . Feijão ;
importar  org . springframework . contexto . anotação . Configuração ;
importar  org . springframework . segurança . autenticação . Gerenciador de Autenticação ;
importar  org . springframework . segurança . configuração . anotação . autenticação . construtores . AuthenticationManagerBuilder ;
importar  org . springframework . segurança . configuração . anotação . método . configuração . EnableGlobalMethodSecurity ;
importar  org . springframework . segurança . configuração . anotação . web . construtores . HttpSegurança ;
importar  org . springframework . segurança . configuração . anotação . web . configuração . Habilitar WebSecurity ;
importar  org . springframework . segurança . configuração . anotação . web . configuração . WebSecurityConfigurerAdapter ;
importar  org . springframework . segurança . configuração . http . SessionCreationPolicy ;
importar  org . springframework . segurança . criptografia . bcrypt . BCryptPasswordEncoder ;
importar  org . springframework . segurança . criptografia . senha . Codificador de Senha ;
importar  org . springframework . segurança . web . autenticação . Nome de usuárioSenhaAuthenticationFilter ;

@ Configuração
@ EnableWebSecurity
@ EnableGlobalMethodSecurity (
        // garantidoEnabled = true,
        // jsr250Enabled = true,
        prePostEnabled = true )
public  class  WebSecurityConfig  estende  WebSecurityConfigurerAdapter {
    @ Autowired
    UserDetailsServiceImpl  userDetailsService ;
    @ Autowired
    private  AuthEntryPointJwt  não autorizadoHandler ;
    @ Feijão
    public  AuthTokenFilter  authenticationJwtTokenFilter () {
        retornar  novo  AuthTokenFilter ();
    }
    @ Substituir
    public  void  configure ( AuthenticationManagerBuilder  authenticationManagerBuilder ) lança  Exception {
        authenticationManagerBuilder . userDetailsService ( userDetailsService ). passwordEncoder ( passwordEncoder ());
    }
    @ Feijão
    @ Substituir
    public  AuthenticationManager  authenticationManagerBean () lança  Exception {
        retorno  super . autenticaçãoManagerBean ();
    }
    @ Feijão
    public  PasswordEncoder  passwordEncoder () {
        retornar  novo  BCryptPasswordEncoder ();
    }
    @ Substituir
    protected  void  configure ( HttpSecurity  http ) lança  Exception {
        http . cora (). e (). csrf (). desabilitar ()
                . manipulação de exceção (). authenticationEntryPoint ( não autorizadoHandler ). e ()
                . SessionManagement (). sessionCreationPolicy ( SessionCreationPolicy . STATELESS ). e ()
                . autorizeRequests (). antMatchers ( "/api/auth/**" ). permitAll ()
                . antMatchers ( "/api/test/**" ). permitAll ()
                . qualquerRequest (). autenticado ();
        http . addFilterBefore ( authenticationJwtTokenFilter (), UsernamePasswordAuthenticationFilter . class );
    }
}
 34 src/main/java/com/arara/araraturismo/security/jwt/AuthEntryPointJwt.java 
@@ -0,0 +1,34 @@
pacote  com . Arara . araraturismo . segurança . jwt ;

importar  java . io . IOException ;
importar  java . útil . Mapa de Hash ;
importar  java . útil . Mapa ;
importar  javax . servlet . ServletException ;
importar  javax . servlet . http . HttpServletRequest ;
importar  javax . servlet . http . HttpServletResposta ;
importar  org . slf4j . Registrador ;
importar  org . slf4j . LoggerFactory ;
importar  org . springframework . http . Tipo de mídia ;
importar  org . springframework . segurança . núcleo . AuthenticationException ;
importar  org . springframework . segurança . web . AuthenticationEntryPoint ;
importar  org . springframework . estereótipo . Componente ;
import  com . mais rápidoxml . jackson . ligação de dados . Mapeador de Objetos ;
@ Componente
public  class  AuthEntryPointJwt  implementa  AuthenticationEntryPoint {
    private  static  final  Logger  Logger = LoggerFactory . getLogger ( AuthEntryPointJwt . class );

    @ Substituir
    public  void  begin ( solicitação HttpServletRequest  , resposta HttpServletResponse , AuthenticationException authException )  
            lança  IOException , ServletException {
        registrador . error ( "Erro não autorizado: {}" , authException . getMessage ());
        resposta . setContentType ( MediaType . APPLICATION_JSON_VALUE );
        resposta . setStatus ( HttpServletResponse . SC_UNAUTHORIZED );
        final  Map < String , Object > body = new  HashMap <>();
        corpo . put ( "status" , HttpServletResponse . SC_UNAUTHORIZED );
        corpo . put ( "erro" , "não autorizado" );
        corpo . put ( "message" , authException . getMessage ());
        corpo . put ( "path" , request .getServletPath ( ) );
        final  Mapeador de  Objetos = new  Mapeador de Objetos ();
        mapeador . writeValue ( resposta . getOutputStream (), corpo );
    }
} 
 51 src/main/java/com/arara/araraturismo/security/jwt/AuthTokenFilter.java 
@@ -0,0 +1,51 @@
pacote  com . Arara . araraturismo . segurança . jwt ;

importar  java . io . IOException ;
importar  javax . servlet . FilterChain ;
importar  javax . servlet . ServletException ;
importar  javax . servlet . http . HttpServletRequest ;
importar  javax . servlet . http . HttpServletResposta ;

import  com . Arara . araraturismo . segurança . serviços . UserDetailsServiceImpl ;
importar  org . slf4j . Registrador ;
importar  org . slf4j . LoggerFactory ;
importar  org . springframework . feijão . fábrica . anotação . Autowired ;
importar  org . springframework . segurança . autenticação . Nome de usuárioSenhaAuthenticationToken ;
importar  org . springframework . segurança . núcleo . contexto . SecurityContextHolder ;
importar  org . springframework . segurança . núcleo . detalhes do usuário . Detalhes do usuário ;
importar  org . springframework . segurança . web . autenticação . WebAuthenticationDetailsSource ;
importar  org . springframework . web . filtro . OncePerRequestFilter ;

 classe  pública AuthTokenFilter  estende  OncePerRequestFilter {
    @ Autowired
    private  JwtUtils  jwtUtils ;
    @ Autowired
    private  UserDetailsServiceImpl  userDetailsService ;
    private  static  final  Logger  Logger = LoggerFactory . getLogger ( AuthTokenFilter.class ) ; _
    @ Substituir
    protected  void  doFilterInternal ( solicitação HttpServletRequest  , resposta HttpServletResponse , FilterChain filterChain )  
            lança  ServletException , IOException {
        tente {
            String  jwt = parseJwt ( request );
            if ( jwt != null && jwtUtils . validateJwtToken ( jwt )) {
                String nome de  usuário = jwtUtils . getUserNameFromJwtToken ( jwt );
                UserDetails  userDetails = userDetailsService . loadUserByUsername ( nome de usuário );

                UsernamePasswordAuthenticationToken  authentication =
                        new  UsernamePasswordAuthenticationToken ( userDetails ,
                                nulo ,
                                userDetails . getAutoridades ());

                autenticação . setDetails ( new  WebAuthenticationDetailsSource (). buildDetails ( request ));
                SecurityContextHolder . getContext (). setAuthentication ( autenticação );
            }
        } catch ( Exceção  e ) {
            registrador . error ( "Não é possível definir a autenticação do usuário: {}" , e );
        }
        filterChain . doFilter ( solicitação , resposta );
    }
    private  String  parseJwt ( solicitação HttpServletRequest  ) {
        String  jwt = jwtUtils . getJwtFromCookies ( request );
        retornar  jwt ;
    }
} 
 72 src/main/java/com/arara/araraturismo/security/jwt/JwtUtils.java 
@@ -0,0 +1,72 @@
pacote  com . Arara . araraturismo . segurança . jwt ;

importar  java . útil . Data ;
importar  javax . servlet . http . Biscoito ;
importar  javax . servlet . http . HttpServletRequest ;

import  com . Arara . araraturismo . segurança . serviços . UserDetailsImpl ;
importar  org . slf4j . Registrador ;
importar  org . slf4j . LoggerFactory ;
importar  org . springframework . feijão . fábrica . anotação . Valor ;
importar  org . springframework . http . Cookie de Resposta ;
importar  org . springframework . estereótipo . Componente ;
importar  org . springframework . web . útil . WebUtils ;
importar  io . jsonwebtoken .*;

@ Componente
 classe  pública JwtUtils {
    private  static  final  Logger  Logger = LoggerFactory . getLogger ( JwtUtils.class ) ; _
    @Value ( "${arara.app.jwtSecret} " )
    private  String  jwtSecret ;
    @Value ( "${arara.app.jwtExpirationMs} " )
    private  int  jwtExpirationMs ;
    @Value ( "${arara.app.jwtCookieName} " )
    private  String  jwtCookie ;

    public  String  getJwtFromCookies ( solicitação HttpServletRequest  ) {
        Cookie  cookie = WebUtils . getCookie ( solicitação , jwtCookie );
        if ( cookie != null ) {
            devolver  o biscoito . obterValor ();
        } senão {
            retornar  nulo ;
        }
    }
    public  ResponseCookie  generateJwtCookie ( UserDetailsImpl  userPrincipal ) {
        String  jwt = generateTokenFromUsername ( userPrincipal . getUsername ());
        Cookie de resposta  = cookie de resposta . de ( jwtCookie , jwt ). caminho ( "/api" ). maxIdade ( 24 * 60 * 60 ). httpSomente ( verdadeiro ). construir ();
        retornar  biscoito ;
    }
    public  ResponseCookie  getCleanJwtCookie () {
        Cookie de resposta  = cookie de resposta . de ( jwtCookie , null ). caminho ( "/api" ). construir ();
        retornar  biscoito ;
    }
    public  String  getUserNameFromJwtToken ( String  token ) {
        retornar  Jwts . analisador (). setSigningKey ( jwtSecret ). parseClaimsJws ( token ). getCorpo (). getAssunto ();
    }
    public  boolean  validateJwtToken ( String  authToken ) {
        tente {
            Jwts . analisador (). setSigningKey ( jwtSecret ). parseClaimsJws ( authToken );
            retorna  verdadeiro ;
        } catch ( SignatureException  e ) {
            registrador . error ( "Assinatura JWT inválida: {}" , e . getMessage ());
        } catch ( MalformedJwtException  e ) {
            registrador . error ( "Token JWT inválido: {}" , e . getMessage ());
        } catch ( ExpiredJwtException  e ) {
            registrador . error ( "O token JWT expirou: {}" , e . getMessage ());
        } catch ( UnsupportedJwtException  e ) {
            registrador . error ( "O token JWT não é suportado: {}" , e . getMessage ());
        } catch ( IllegalArgumentException  e ) {
            registrador . error ( "A string de declarações JWT está vazia: {}" , e . getMessage ());
        }
        retornar  falso ;
    }

    public  String  generateTokenFromUsername ( String nome de  usuário ) {
        retornar  Jwts . construtor ()
                . setAssunto ( nome de usuário )
                . setIssuedAt ( nova  data ())
                . setExpiration ( new  Date (( new  Date ()). getTime () + jwtExpirationMs ))
                . signWith ( SignatureAlgorithm . HS512 , jwtSecret )
                . compacto ();
    }
} 
 85 src/main/java/com/arara/araraturismo/security/services/UserDetailsImpl.java 
@@ -0,0 +1,85 @@
pacote  com . Arara . araraturismo . segurança . serviços ;

importar  java . útil . Coleta ;
importar  java . útil . Lista ;
importar  java . útil . Objetos ;
importar  java . útil . fluxo . Coletores ;

import  com . Arara . araraturismo . modelos . Usuário ;
importar  org . springframework . segurança . núcleo . Autoridade Concedida ;
importar  org . springframework . segurança . núcleo . autoridade . SimpleGrantedAuthority ;
importar  org . springframework . segurança . núcleo . detalhes do usuário . Detalhes do usuário ;
import  com . mais rápidoxml . jackson . anotação . JsonIgnore ;

public  class  UserDetailsImpl  implementa  UserDetails {
    private  estático  final  longo  serialVersionUID = 1L ;
     ID Longo  privado ;
    private  String nome de  usuário ;
     e- mail privado String  ;
    @JsonIgnore _
     senha privada String  ;
     coleção particular <? estende  GrantedAuthority > autoridades ;

    public  UserDetailsImpl ( Long  id , String  username , String  email , String  password ,
                           Coleção <? estende  GrantedAuthority > autoridades ) {
        isso . id = id ;
        isso . nome de usuário = nome de usuário ;
        isso . e- mail = e- mail ;
        isso . senha = senha ;
        isso . autoridades = autoridades ;
    }
    public  static  UserDetailsImpl  build ( User  user ) {
        List < GrantedAuthority > autoridades = usuário . getRoles (). fluxo ()
                . map ( role -> new  SimpleGrantedAuthority ( role . getName (). name ()))
                . collect ( Collectors . toList ());
        retornar  novo  UserDetailsImpl (
                usuário . getId (),
                usuário . getUsuário (),
                usuário . getEmail (),
                usuário . obterSenha (),
                autoridades );
    }
    @ Substituir
     Coleção pública <? extends  GrantedAuthority > getAuthorities () {
         autoridades de retorno ;
    }
    public  Long  getId () {
         ID de retorno ;
    }
    public  String  getEmail () {
         e-mail de retorno ;
    }
    @ Substituir
    public  String  getPassword () {
        retornar  senha ;
    }
    @ Substituir
    public  String  getUsername () {
        retornar nome de  usuário ;
    }
    @ Substituir
    public  boolean  isAccountNonExpired () {
        retorna  verdadeiro ;
    }
    @ Substituir
    public  boolean  isAccountNonLocked () {
        retorna  verdadeiro ;
    }
    @ Substituir
    public  boolean  isCredentialsNonExpired () {
        retorna  verdadeiro ;
    }
    @ Substituir
    public  boolean  isEnabled () {
        retorna  verdadeiro ;
    }
    @ Substituir
    public  boolean  equals ( Object  o ) {
        se ( isso == o )
            retorna  verdadeiro ;
        if ( o == null || getClass () != o . getClass ())
            retornar  falso ;
        UserDetailsImpl  user = ( UserDetailsImpl ) o ;
         objetos de retorno . igual a ( id , usuário . id );
    }
} 
 23 src/main/java/com/arara/araraturismo/security/services/UserDetailsServiceImpl.java 
@@ -0,0 +1,23 @@
pacote  com . Arara . araraturismo . segurança . serviços ;

import  com . Arara . araraturismo . modelos . Usuário ;
import  com . Arara . araraturismo . repositórios . UserRepository ;
importar  org . springframework . feijão . fábrica . anotação . Autowired ;
importar  org . springframework . segurança . núcleo . detalhes do usuário . Detalhes do usuário ;
importar  org . springframework . segurança . núcleo . detalhes do usuário . UserDetailsService ;
importar  org . springframework . segurança . núcleo . detalhes do usuário . Nome de usuárioNotFoundException ;
importar  org . springframework . estereótipo . Serviço ;
importar  org . springframework . transação . anotação . Transacional ;

@ Serviço
public  class  UserDetailsServiceImpl  implementa  UserDetailsService {
    @ Autowired
    UserRepository  userRepository ;
    @ Substituir
    @ Transacional
    public  UserDetails  loadUserByUsername ( String  username ) throws  UsernameNotFoundException {
        Usuário  usuário = userRepository . findByUsername ( nome de usuário )
                . orElseThrow (() -> new  UsernameNotFoundException ( "Usuário não encontrado com nome de usuário: " + nome de usuário ));
        return  UserDetailsImpl . construir ( usuário );
    }
} 
 10 src/main/resources/application.properties 
@@ -0,0 +1,10 @@

spring.datasource.url = jdbc:mysql://localhost:3306/testdb2?useSSL=false
spring.datasource.username = root
spring.datasource.password = 1234
spring.jpa.properties.hibernate.dialect = org.hibernate.dialect.MySQL5InnoDBDialect
spring.jpa.hibernate.ddl-auto = atualizar
# Propriedades do aplicativo
arara.app.jwtCookieName = araraturismo
arara.app.jwtSecret = araraTurismoSecretKey
arara.app.jwtExpirationMs = 86400000 
 13 src/test/java/com/arara/araraturismo/AraraTurismoApplicationTests.java 
@@ -0,0 +1,13 @@
pacote  com . Arara . araraturismo ;

importar  org . junho . júpiter . api . Teste ;
importar  org . springframework . inicialização . teste . contexto . SpringBootTest ;

@ SpringBootTest
class  AraraTurismoAplicativoTestes {

	@ Teste
	void  contextLoads () {
	}

}
