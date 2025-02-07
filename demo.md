## Check consumer unit tests

    make unit

## Run consumer agains the provider

    make run-provider 
    make run-consumer

👉 The consumer request fails

![Unit Test With Mocked Response](diagrams/workshop_step2_unit_test.png)

📣 Doh! The Provider doesn't know about /users/:id. On closer inspection, the provider only knows about /user/:id and /users

## Create a pact contract

    make consumer

👉 A pact file has been generated into the folder /pacts

![Test using Pact](diagrams/workshop_step3_pact.png)

## Check the provider match the contract

    make provider


![Pact Verification](diagrams/workshop_step4_pact.png)

## Using pack broker

![Broker collaboration Workflow](diagrams/workshop_step10-broker.png)

```console
docker compose up
```

login: pact_workshop

### Publish from consumer pact

```console
    make publish
```

### Test the provider again

⚠ Comment the filepath import
⚠ Update the provider pact tests to use the broker

```console
make provider
```