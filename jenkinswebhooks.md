# GitHub Webhook and Jenkins Generic Webhook Configurations steps

## step-1:

-   Install `Generic Webhook Trigger` Plugin in Jenkins
-   Configure Jenkins Pipeline Configuration via ticked `Generic Webhook trigger`
-   Copy `Is triggered by HTTP requests to http://JENKINS_URL/generic-webhook-trigger/invoke`
by following this pattern `http://IP/Domain:8080/generic-webhook-trigger/invoke?token=km1nrYigA4JTz3Rb86DmOqz8v2mwejm17ZD`

```bash
# use this command for generate random secret

head -c 32 /dev/urandom | base64
```

-   In `Post content parameters` section
    -   **Variable:** ref
    -   **Expression:** $.ref
    -   **Ticked** JSONPath
    -   **Variable Name of variable:** repo
    -   **Expression:** $.repository.full_name
    -   **Ticked** JSONPath
    -   **Header parameters:** Request header > X-GitHub-Event
    -   **Token:** Your generated token by Random Secret command
    -   **Cause:** Triggered on $ref
    -   **Ticked:** `Print post content` and `Print contributed variables`
    -   **Optional filter > Expression:** ^refs/heads/BRANCH_NAME GITHUB_USERNAME/REPO_NAME push$
        -   change `BRANCH_NAME`  `GITHUB_USERNAME` and `REPO_NAME` according to your repository
    -   **Text:** $ref $repo $x_github_event

## Step-2:

-   In GitHub open your repository
-   In Project repository > `Settings`
-   On the left-hand side click `Webhooks` and click `Add webhook` button
-   Place your full Jenkins Generic Webhook URL in `Payload URL *` section
    -   ```bash
        http://IP/Domain:8080/generic-webhook-trigger/invoke?token=YOUR-GENERETED-SECRET
        ```
-   Under `Content type *` Select `application/json`
-   If your Jenkins URL don't have SSL or HTTPS then select 
    -   `Disable (not recommended)`
    - Otherwise  `Enable SSL verification`
- Under `Which events would you like to trigger this webhook?` Select `Just the push event.`
-   `Active` should be Ticked
-   Press `Add webhook` button to finish

## Step-3V# GitHub Webhook and Jenkins Generic Webhook Configurations steps

## step-1:

-   Install `Generic Webhook Trigger` Plugin in Jenkins
-   Configure Jenkins Pipeline Configuration via ticked `Generic Webhook trigger`
-   Copy `Is triggered by HTTP requests to http://JENKINS_URL/generic-webhook-trigger/invoke`
by following this pattern `http://IP/Domain:8080/generic-webhook-trigger/invoke?token=km1nrYigA4JTz3Rb86DmOqz8v2mwejm17ZD`

```bash
# use this command for generate random secret

head -c 32 /dev/urandom | base64
```

-   In `Post content parameters` section
    -   **Variable:** ref
    -   **Expression:** $.ref
    -   **Ticked** JSONPath
    -   **Variable Name of variable:** repo
    -   **Expression:** $.repository.full_name
    -   **Ticked** JSONPath
    -   **Header parameters:** Request header > X-GitHub-Event
    -   **Token:** Your generated token by Random Secret command
    -   **Cause:** Triggered on $ref
    -   **Ticked:** `Print post content` and `Print contributed variables`
    -   **Optional filter > Expression:** ^refs/heads/BRANCH_NAME GITHUB_USERNAME/REPO_NAME push$
        -   change `BRANCH_NAME`  `GITHUB_USERNAME` and `REPO_NAME` according to your repository
    -   **Text:** $ref $repo $x_github_event

## Step-2:

-   In GitHub open your repository
-   In Project repository > `Settings`
-   On the left-hand side click `Webhooks` and click `Add webhook` button
-   Place your full Jenkins Generic Webhook URL in `Payload URL *` section
    -   ```bash
        http://IP/Domain:8080/generic-webhook-trigger/invoke?token=YOUR-GENERETED-SECRET
        ```
-   Under `Content type *` Select `application/json`
-   If your Jenkins URL don't have SSL or HTTPS then select 
    -   `Disable (not recommended)`
    - Otherwise  `Enable SSL verification`
- Under `Which events would you like to trigger this webhook?` Select `Just the push event.`
-   `Active` should be Ticked
-   Press `Add webhook` button to finish

## Step-3

-   Finally test webhook by changes or push in the specific repo branch.

## Troubleshooting Step
-   `For Trouble Shooting Please contact with Claude Mama`

-   Finally test webhook by changes or push in the specific repo branch.

## Troubleshooting Step
-   `For Trouble Shooting Please contact with Claude Mama`