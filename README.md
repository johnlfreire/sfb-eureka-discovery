# sfb-eureka-discovery


Algumas notas importantes sobre Eureka: Um aplicativo registrado em Eureka é conhecido
como instância de Eureka. Cada instância de Eureka também é um Cliente Eureka, pois
pode buscar os detalhes de outras instâncias de Eureka também.

Se estamos usando o servidor Eureka no modo autônomo, ou seja, há apenas um servidor Eureka, então precisamos definir e falso para que ele não tente se registrar consigo mesmo, pois o servidor Eureka também tem um cliente Eureka embutido.eureka.client.fetch-registryeureka.client.register-with-eureka

Um serviço é registrado no servidor Eureka quando o é definido como verdadeiro (por padrão, verdadeiro) e se torna uma instância Eureka. Então este caso continua enviando batimentos cardíacos para o servidor Eureka. Se o servidor Eureka não receber um heartbeats "batimento cardíaco" de qualquer instância dentro de um determinado limite de tempo (por padrão, 30 seg) então ele considerará essa instância como DOWN e irá desregistrá-la do registro do serviço.eureka.client.register-with-eureka

Uma instância de Eureka também é um cliente Eureka, pois busca o registro do servidor Eureka contendo os detalhes de outras instâncias. Para habilitá-lo, é definido como verdadeiro (por padrão, verdadeiro). Assim que um serviço se registra com o servidor, ele busca o registro e o pega. Ele continua verificando o registro em intervalo regular (por padrão, 30 segundos) e se houver alguma alteração no registro, ele busca apenas a atualização e a parte inalterada ainda é usada a partir do cache.eureka.client.fetch-registry

Cada instância de Eureka usa um ponto final de serviço, a fim de obter uma lista de todas as instâncias dos serviços registrados no registro. Também podemos ver todas as instâncias registradas em Discovery Client Service Instance http://localhost:5555/eureka/app
