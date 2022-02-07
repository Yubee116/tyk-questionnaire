# Tyk Questionnaire

Tyk Questionnaire is a GH repo that lists Tyk specific configuration files for the take home assignment. Questions are purposely left blank on this GH repo to encourage a dynamic list each time.

## Prerequisites

Follow the [Tyk Pro Docker Demo](https://github.com/TykTechnologies/tyk-pro-docker-demo) Github Repo to set up a local environment. Copy and paste the relevant *.env files from this repo onto the appropriate files from the Tyk Pro Docker Demo to replicate each question.

**Friendly reminder that for Tyk Pro Docker Demo you will need an active License. Please reach out for a trial license**

## Usage

Once you've copied the relevant configuration files over, please call below command in your Tyk Pro Docker Demo root folder to replicate the questionnaires locally.

```bash
docker-compose up
```

To see the new changes from your configuration files you'll need to `down` your environment and then `up` it again.

```bash
docker-compose down
```

For any question that has only the API definition please import it onto your environment for testing purposes.