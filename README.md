# Sample repo to demonstate the creation of GitHub repo using Terraform code

More information about GitHub provider and available resources is [here](https://registry.terraform.io/providers/integrations/github/latest/docs)


# Prerequisites

Install and configure Terraform as per [official documentation](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)

Have GitHub token.

To generate token, login to your GitHub account, click on the profile icon (in the top-right corner of the screen) and select **Settings**:

![Screenshot 2023-05-23 at 16 38 24](https://github.com/dmitryuchuvatov/github-provider/assets/119931089/e457f7db-97d0-4bf8-87b7-86696a1aa451)

Scroll down to **Developer settings** -> select **Personal access tokens** -> **Tokens (Classic)**

![Screenshot 2023-05-23 at 16 38 44](https://github.com/dmitryuchuvatov/github-provider/assets/119931089/f556064e-7a38-405c-a174-d11e50543233)

Click on **Generate new token** -> **Generate new token (Classic)**

![Screenshot 2023-05-23 at 16 38 54](https://github.com/dmitryuchuvatov/github-provider/assets/119931089/512f3ada-b6cc-4551-be79-fccae3d7c74f)

Click on **Generate new token** -> **Generate new token (Classic)**

![Screenshot 2023-05-23 at 16 39 27](https://github.com/dmitryuchuvatov/github-provider/assets/119931089/44775734-8ba5-4de5-b099-00298b029b0b)

Make sure to copy the newly generated token!

# How To

## Clone repository

```
git clone https://github.com/dmitryuchuvatov/github-provider.git
```

## Change folder

```
cd github-provider
```

## Initialize Terraform

```
terraform init
```

## Run Terraform Plan

```
terraform plan
```

## Run Terraform Apply

```
terraform apply
```
When prompted, paste your token and hit **Enter**, then enter **yes** and hit **Enter** again to apply:

```
var.token
  GitHub API Token

  Enter a value: 


Terraform used the selected providers to generate the following execution plan. Resource actions are indicated
with the following symbols:
  + create

Terraform will perform the following actions:

  # github_repository.example will be created
  + resource "github_repository" "example" {
      + allow_auto_merge            = false
      + allow_merge_commit          = true
      + allow_rebase_merge          = true
      + allow_squash_merge          = true
      + archived                    = false
      + default_branch              = (known after apply)
      + delete_branch_on_merge      = false
      + description                 = "my awesome codebase"
      + etag                        = (known after apply)
      + full_name                   = (known after apply)
      + git_clone_url               = (known after apply)
      + html_url                    = (known after apply)
      + http_clone_url              = (known after apply)
      + id                          = (known after apply)
      + merge_commit_message        = "PR_TITLE"
      + merge_commit_title          = "MERGE_MESSAGE"
      + name                        = "example"
      + node_id                     = (known after apply)
      + private                     = (known after apply)
      + repo_id                     = (known after apply)
      + squash_merge_commit_message = "COMMIT_MESSAGES"
      + squash_merge_commit_title   = "COMMIT_OR_PR_TITLE"
      + ssh_clone_url               = (known after apply)
      + svn_url                     = (known after apply)
      + visibility                  = "public"
    }

Plan: 1 to add, 0 to change, 0 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

github_repository.example: Creating...
github_repository.example: Creation complete after 6s [id=example]

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
```

To verify the results, navigate to your list of repositories and locate the repo: 

![Screenshot 2023-05-30 at 09 39 43](https://github.com/dmitryuchuvatov/github-provider/assets/119931089/c086a23a-c91e-48f5-802b-8612ee387101)

## Run Terraform Destroy

```
terraform destroy
```

