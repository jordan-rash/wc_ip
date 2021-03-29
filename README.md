`docker-compose up -d`  
`wash drain all`   
`make release`  
`wash reg push localhost:5000/ip:0.1.0 target/wasm32-unknown-unknown/release/client_test_s.wasm --insecure`  
`export CLIENT_ACTOR=$(wash claims inspect localhost:5000/ip:0.1.0 --insecure -o json | jq -r '.module')`  
`RUST_LOG=info wasmcloud --allowed-insecure localhost:5000 -m manifest.yaml`  

```
❯ curl localhost:8080
2.3.4.5
```
