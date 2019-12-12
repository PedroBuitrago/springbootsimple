# springbootsimple
Proyecto basado en springboot que cuenta con dos interfaces, una web y otra REST. La interface web permite listar usuarios de una base de datos y obtener los ultimos tweets. La interface REST permite obtener la info de un usuario y actualizarlo.

Instrucciones para Ejecución

1. Descargue el proyecto
2. Por medio de maven ejecutar un clean & install
3. Ejecute la clase com.zemoga.devtesting.portfolio.PortfolioApplication

Esta aplicación está basada en springboot de tal manera que no es necesario hacer ninguna configuración en servidores externos, la aplicación subirá un servidor Tomcat.

Instrucciones para visualziación Web
4. Una vez la aplicación corra, abra un navegador (preferiblemente chrome) con el URL http://localhost:8080/
5. Haga clic en el url "here", esta acción le presentará todos los perfiles que se encuentran almacenados en la base de datos referenciada
6. Escoja cualquiera de las filas haciendo clic en el URL del ID
7. Visualice el portafolio del perfil seleccionado

Instrucciones para interacción API Rest

GET INFO
8. Por medio del cliente REST de su predilección, configure un request HTTP GET con el URL http://localhost:8080/zemoga_portfolio_api/userinfo/<ID> donde el ID corresponde al identificador idportfolio de la base de datos de referencia, por ejemplo http://localhost:8080/zemoga_portfolio_api/userinfo/10
  
La respuesta será sera un JSON como el siguiente:

{"id":10,"imageURL":"https://www.eltiempo.com/files/article_main/uploads/2019/06/12/5d01078005da1.jpeg","title":"Chris Froome","description":"The best cyclist of the history of course","twitter":"chrisfroome","tweets":null}

SET INFO
9. Para guardar información, nuevamente utilice el cliente REST de su predilección, configure un request HTTP POST con el siugiente URL
http://localhost:8080/zemoga_portfolio_api/modify_user_info/<ID> donde el ID corresponde al identificador idportfolio de la base de datos de referencia, por ejemplo http://localhost:8080/zemoga_portfolio_api/modify_user_info/10
  
 En el campo body y en formato application/json configure un json siguiente el siguiente template
 
 {
  "image":"https://www.eltiempo.com/files/article_main/uploads/2019/06/12/5d01078005da1.jpeg",
  "name":"XYZYZYZYZ"
  "description":"Esta es una description"
}

Es importante anotar, que la variable name será mapeada al campo title en la tabla portfolio de la base de datos de referencia

  
  




