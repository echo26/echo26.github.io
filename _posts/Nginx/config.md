# configuration file

Configuration file Architecture

```

Core Funtionality (Define how Nginx works)

worker_processes
pid
events
error_log
worker_rlimit_nofile
...


#http contenxt (Define http configuratione of Nginx)
http {

      # server context (Define ip address / port and server_name to upstream/ within http context)
      server {
      
          # loccation context (Define relational qualities with server contexts.)
          location match_modifier location_match {
          
          }
      
      }
      
      # upstream context (pass requests of the pool of servers. within http context)
      upstream {
      }
      
      

}
```


