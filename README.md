## IG output

* [CI Build](https://build.fhir.org/ig/HL7nl/fhir-ig-sandbox-stu3/)
* [Web-based editor](https://github.dev/HL7nl/fhir-ig-sandbox-stu3/)
* [Auto-IG build dashboard](https://fhir.github.io/auto-ig-builder/)

## Validate resources
```
(optional) > curl -L https://github.com/hapifhir/org.hl7.fhir.core/releases/latest/download/validator_cli.jar -o validator_cli.jar
> java -jar validator_cli.jar -version 3.0.2 input/resources -ig input/resources
```

## To build the IG (need minimal version 1.2.31 dd 1-feb-2023 ivm zib2017 package fix)
```
(optional)> curl -L https://github.com/HL7/fhir-ig-publisher/releases/latest/download/publisher.jar -o publisher.jar
> java -jar publisher.jar -ig ig.ini
```

### Trigger FHIR auto-ig builder
```
curl -X POST  "https://us-central1-fhir-org-starter-project.cloudfunctions.net/ig-commit-trigger" \
  -H "Content-type: application/json" \
  --data '{"ref": "refs/heads/snapshot", "repository": {"full_name": "HL7nl/fhir-ig-sandbox-stu3"}}'
```
