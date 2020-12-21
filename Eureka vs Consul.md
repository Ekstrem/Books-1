[Comparison of Spring Cloud with Eureka vs. Consul.io](https://www.nvisia.com/insights/comparison-of-spring-cloud-with-eureka-vs.-consul)
[Consul vs Eureka](https://stackshare.io/stackups/consul-vs-eureka)

# https://gist.github.com/StevenACoffman/de394d6511a387ada9ab988e33be8583
> Could you please file a ticket? We can hopefully get this done in more detail, but in gist:

> ## Eureka

> * AP (Слабая согласованность), состояние реплицируется с “наибольшей эффективностью”
> * Сервисы зарегистрированы на одном сервере, который пытается реплицироваться на другие серверы.
> * Регистрации служб имею TTL
> * Reads are routed to any server, can be stale or missing data
> * Scales well due to low coordination, especially when server failures relatively rare
> * Fails if all servers down

> ## Consul

> * CP (strong consistency), state is replicated using Raft
> * Services registered with any server, but written via Raft to a quorum
> * Registrations have complex health checks, including gossip failure detection instead of heartbeating
> * Reads routed to any server, consistent by default but stale reads can be requested
> * Stale reads scale well, Consistent reads scale to tens of thousands per second
> * Consistency offers locking and cluster coordination
> * Lots more features (health checking, locking, KV, federation, ACLs)
> * Fails if a majority of servers down

> Best Regards,
> Armon Dadgar
