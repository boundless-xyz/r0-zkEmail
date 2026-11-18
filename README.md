> **Archived:** This repository is no longer maintained and is preserved for reference. For context on the Boundless ZK proving protocol pause and transition, see the [Boundless Foundation announcement](https://boundlessfdn.org/blog/zkc-the-ai-access-coin).

# RISC Zero zkEmail

This repository contains a RISC Zero project to verify DKIM signatures. With r0-zkEmail, email authenticity can be verified through zero-knowledge proofs, removing the need for direct access to email content. Instead, zk-DKIM generates cryptographic proofs that confirm the signature’s validity while keeping sensitive data private.

## Installation

Clone the repository and navigate into it. 

```
git clone https://github.com/risc0-labs/r0-zkEmail.git

cd r0-zkEmail
```

## Usage

To run the program, we need to download an email. In Google Mail, navigate to an email and use the hamburger menu to download the `.eml` file associated with the email. We then need to run our host, which will accept the domain and path to the email in order to verify the DKIM header. 

```
RISC0_DEV_MODE=1 RUST_LOG=info cargo run --release -- <FROM_DOMAIN> <EMAIL_PATH>
```

#### Parameters

- `<FROM_DOMAIN>`: The domain the email comes from. For example, an email from Google Mail account will be `gmail.com`
- `<EMAIL_PATH>`: The path to the email `.eml` file.

### Example

```
RISC0_DEV_MODE=1 RUST_LOG=info cargo run --release -- example.com example.eml
```

## Disclaimer
Use it at your own risk. This repository is experimental and unaudited. Do not use in production. 

## License

This project is licensed under the Apache2 license. See [LICENSE](https://github.com/risc0-labs/r0-zkEmail/blob/main/LICENSE).

