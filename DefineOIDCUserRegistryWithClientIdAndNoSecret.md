## What is this for

This describes how to create an OIDC user registry on IBM APIConnect, with the following characteristics
- Client ID only
- NO Client Secret
  - Client Certificate is used, in place of Client Secret


#### Step 1: Create TLS Client Profile with client public/private/truststore

From the UI -> Resources -> TLS -> {Keystore, Truststore, TLS Client Profile}

<img width="589" alt="image" src="https://user-images.githubusercontent.com/24717424/214154480-0fd4535b-d0ef-421a-8123-a02bdb21f883.png">

<img width="1045" alt="image" src="https://user-images.githubusercontent.com/24717424/214154981-6471b616-2a39-4489-a615-0138176cdee8.png">


### Step 2: Create OIDC User Registry

From the UI -> Resources -> User registries -> Create -> OpenID Connect (OIDC)

- Select the type, provide title

<img width="1175" alt="image" src="https://user-images.githubusercontent.com/24717424/214155590-88265a48-6232-40ae-8a62-c00e1c5d3c1b.png">

- Provide authorize, token endpoints and **important** the TLS client profile for the mutual TLS communication with token endpoint

<img width="845" alt="image" src="https://user-images.githubusercontent.com/24717424/214155702-f0f4ccaa-9a29-45f5-8487-b887f09c92be.png">

- In the Client Information section, select "Data encoded form body" and provide "Client Id"

<img width="871" alt="image" src="https://user-images.githubusercontent.com/24717424/214155909-a0605bd0-7800-481c-b8b5-4e223ae580ec.png">
