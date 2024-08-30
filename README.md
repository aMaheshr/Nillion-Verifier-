![Verifier-Program-5_2-](https://github.com/user-attachments/assets/8c01fe52-3a60-4159-82f0-9f29468b0fba)



<h1 align="center"> Nillion Verifier </h1>

## Basic Steps :

- [Keplr wallet](https://chromewebstore.google.com/detail/keplr/dmkamcknogkgcdfhhbddcghachkejeap?hl=en)
- [Faucet](https://faucet.testnet.nillion.com/)
- [Nillion Verifier](https://verifier.nillion.com/verifier)

## Lets Start 

### Install Docker 

```console
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
### check Docker version

```console
docker --version
```
Return output : Docker version 27.1.1, build 63125853e3

### Run the hello world container

```console
docker container run --rm hello-world
```
output :“Hello from Docker!”

### Accuser image

```console
docker pull nillion/retailtoken-accuser:v1.0.0
```

### intialise  the accuser

```console
mkdir -p nillion/accuser
```

```console
docker run -v ./nillion/accuser:/var/tmp nillion/retailtoken-accuser:v1.0.0 initialise
```
- u can check Credentials list : sudo cat /root/nillion/accuser/credentials.json 
- Register using pub_key & Address : https://verifier.nillion.com/verifier
- Claim faucet with ur new Address

### Run Accuser 

- YOU MUST WAIT 30-60 MINUTES TO CONTINUE WITH THE STEPS BELOW. The secret verification is designed wait for a period of time before fully registering the accuser

```console
docker run -v ./nillion/accuser:/var/tmp nillion/retailtoken-accuser:v1.0.0 accuse --rpc-endpoint "https://testnet-nillion-rpc.lavenderfive.com" --block-start 5105545
```
- any RPC Error first stop Docker & remove given below Cmds & change rpc 
---------------------------------------------------------------------------------------------
### check Logs

```console
docker ps
```

- copy ur container id

```console
docker logs -f <your container ID>
```
### Stop Docker 

```console
docker stop <Container id>
```
```console
docker rm <container id>
```

Thats it 🎉

FOllow on X : https://x.com/CryptoCrocks
