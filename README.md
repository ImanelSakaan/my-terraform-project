# My-terraform-project
CST8918 Hybrid-A09 Husky and GitHub Actions

## ✅ GitHub Actions workflow
### What’s the goal of this part in the Lab?
- GitHub Actions will **fail** when there's a formatting or syntax error in a `.tf` file.
- And **pass** when the error is fixed.
- 
### Step 1: Create a new branch from `main`
In terminal:

```bash
git checkout -b test-terraform
````
This creates and switches to a new branch called `test-pr`.

---
### ✍️ Step 2: Make a change (if you haven’t yet)
Edit `main.tf` file :

* Fix an existing one (to test success)
---

### 💾 Step 3: Commit and push the new branch
```bash
git add .
git commit -m "testing GitHub Actions"
git push origin test-terraform
```
<img width="712" alt="image" src="https://github.com/user-attachments/assets/a334a6b5-ebd8-4325-8ec1-20cc84901c82" />

<img width="700" alt="image" src="https://github.com/user-attachments/assets/fff530e0-5172-4d35-a648-2cbac42b21ac" />


<img width="965" alt="image" src="https://github.com/user-attachments/assets/07d45387-161f-4d30-a5a4-255d68efad7e" />

<img width="713" alt="image" src="https://github.com/user-attachments/assets/ad6d2c27-d79a-4dfe-8180-ae5135c129ad" />


<img width="695" alt="image" src="https://github.com/user-attachments/assets/2dc9d8df-f2db-47e3-b47e-68952008cb00" />

## ✅ Add Another GitHub Actions Job (Terraform Validation)
1. **Open your GitHub Actions workflow file** (usually located at `.github/workflows/terraform.yml`).
2. **Under the `jobs:` section, add the following job:**


```yaml
jobs:
  validate_script:
    runs-on: ubuntu-latest
    name: terraform validate check
    steps:
      - uses: actions/checkout@v3

      - name: Setup Terraform
        uses: hashicorp/setup-terraform@v2
        with:
          terraform_version: 1.2.4

      - name: Terraform Init
        run: terraform init

      - name: Terraform Validate
        run: terraform validate
```

<img width="1247" alt="image" src="https://github.com/user-attachments/assets/80cc2120-a71f-49ff-b8c6-e7ebd39e83ea" />


