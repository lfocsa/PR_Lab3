## Lucrare de Laborator Nr.3

### Scop:
__1. Studierea protocolului Http si utilizarea in Web communication;__

__2. Informarea despre Java components responsabile pentru implementarea Http methods;__

__3. Crearea unui client app care suporta principalele Http methods folosind [httpbin.org](httpbin.org);__

### Sarcina:
Implementați un client HTTP care ar trebui să utilizeze metodele HTTP pentru a efectua requests.

Pentru a implementa aplicația am folosit Apache Maven - un instrument de automatizare al construirii,
care mi-a dat de asemenea templateul proiectului. Fișierul care conduce structura proiectului, dependențele și alte bunuri este numit _ ** pom.xml ** _. 
În acest fișier la dependențe am inclus următorul bloc:
```
<dependency>
    <groupId>org.apache.httpcomponents</groupId>
    <artifactId>httpclient</artifactId>
    <version>4.5.6</version>
</dependency>
```
În Java există mai multe moduri de a efectua cererile HTTP,am ales să folosesc _** HttpUrlConnection **_ care
face legătura dintre Browser și Server. Clasa UrlConnection are o mulțime de metode 
și funcții pentru realizarea funcționalității conexiunilor și a requestsurilor. 
Eu am clasa principală unde am USER_AGENT și apelul pentru fiecare metodă.
```
public class HttpClientRequest {
    private static final String USER_AGENT = "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/72.0.3626.121 Safari/537.36";

    private static final String GET_URL = "https://httpbin.org/get";
    private static final String POST_URL = "https://httpbin.org/post";
    private static final String DELETE_URL = "https://httpbin.org/delete";
    private static final String IMAGE_URL = "https://httpbin.org/image";

    public static void main(String[] args) throws Exception {

        sendGET();
        sendPost();
        sendDelete();
        getImage();
    }
    ```
