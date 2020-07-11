# Terraform-Cloudflare-Maintenance

Dead simple Terraform module to create a *Maintenance Page* using Cloudflare Workers. You can [preview the page here](https://hodovi.cc/maintenance/).

![Preview](https://i.imgur.com/taxwrht.png)

# Usage

Simple maintenance page with your logo, font and email.

module "hodovi_cc_maintenance" {
  source          = "git::git@github.com:adinhodovic/terraform-cloudflare-maintenance.git?ref=v0.1.0"
  cloudflare_zone = "hodovi.cc"
  pattern         = "hodovi.cc/maintenance/*"
  company_name    = "HoneyLogic"
  email           = "support@honeylogic.io"
  font            = "Poppins"
  logo_url        = "https://s3.eu-west-1.amazonaws.com/honeylogic.io/media/images/Honeylogic_-_icon.original.height-80.png"
}

# Inputs

| Variable        | Description                                                  | Required | Type                                           | Default       |
|-----------------|:------------------------------------------------------------:|:--------:|:----------------------------------------------:|:-------------:|
| cloudflare_zone | The Cloudflare Zone                                          | True     | String                                         | -             |
| pattern         | The DNS pattern to apply the Maintenance page to             | True     | String                                         | -             |
| email           | The email address for support                                | True     | String                                         | -             |
| company_name    | Company name                                                 | True     | String                                         | -             |
| font            | The font for the page                                        | false    | String                                         | "Poppins"     |
| white_list_ips  | The IPS that are whitelisted to bypass the maintenance page. | false    | List separated by commas e.g "1.1.1.1,2.2.2.2" | "placeholder" |
| logo_url        | The logo to be displayed                                     | True     | String                                         | -             |

Example can be found in examples/root-example.
