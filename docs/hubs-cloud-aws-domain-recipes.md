---
id: hubs-cloud-aws-domain-recipes
title: Domain Recipes
sidebar_label: Domain Recipes
---
[Original](https://hubs.mozilla.com/docs/hubs-cloud-aws-domain-recipes.html)

<!-- When creating your Hubs Cloud stack on AWS you will be asked to provide a number of domains: -->
AWSで Hubs Cloud のスタックを作成する場合、以下のドメインを指定が求められます。

- **サイトのドメイン名 (Site Domain Name)**
- **内部ドメイン (Internal Domain)**
- **ショートリンクのためのドメイン (Short Link Domain)**
- **外部発信できるメールのためのドメイン (Outgoing Email Domain)**
- Your **外部発信するメールのサブドメイン (Outgoing Email Subdomain Prefix)**

<!-- This guide provides a few recipes for setting up your domains before creating your stack. -->
このガイドでは、スタックを作成する前にドメインを設定するためのいくつかのレシピを提供します。

<!-- To simplify setup, it's highly recommended you transfer any relevant domains to Route 53, since Hubs Cloud will then be able to manage DNS and SSL certificate renewals for you. -->
セットアップを簡略化するために、関連するドメインを Route 53 に転送することを強くお勧めします。Hubs Cloud はDNSおよびSSL証明書の更新を管理できるようになります。

### レシピ 1: Route 53 での専用ドメイン

- You want to run your site on the top level domain `myhub.com`
- `myhub.com` is registered on Route 53.
- You want short links on `myhub.link`, and mail from `mail.myhub.com`
- You are *not* using `myhub.com` for other sites or purposes

#### レシピ:

- Register and set up `myhub.link` on Route 53.
- Specify the following when creating the stack:
  - **Site Domain Name**: `myhub.com`
  - **Site is Set Up On Route 53**: `Yes`
  - **Internal Domain**: `myhub.com`
  - **Short Link Domain**: `myhub.link`
  - **Outgoing Email Domain**: `myhub.com`
  - **Outgoing Email Subdomain Prefix**: `mail`

### レシピ 2: Route 53 での専用サブドメイン

- You want to run your site on the top level domain `hub.mysite.com`
- `mysite.com` is registered on Route 53.
- You want short links on `myhub.link`, and mail from `mail.mysite.com`
- You are *not* using `mysite.com` for other sites or purposes

#### レシピ:

- Register and set up `myhub.link` on Route 53.
- Specify the following when creating the stack:
  - **Site Domain Name**: `hub.mysite.com`
  - **Site is Set Up On Route 53**: `Yes`
  - **Internal Domain**: `mysite.com`
  - **Short Link Domain**: `myhub.link`
  - **Outgoing Email Domain**: `mysite.com`
  - **Outgoing Email Subdomain Prefix**: `mail`

### レシピ 3: Route 53 での共用ドメイン

- You want to run your site on the top level domain `hub.mysite.com`
- `mysite.com` is registered on Route 53.
- You want short links on `myhub.link`, and mail from `mail.mysite.com`
- You are *are* using `mysite.com` for other sites or purposes

#### レシピ:

- Register and set up `myhub.link` on Route 53.
- Register and set up an *internal domain* on Route 53. This can be any name you want, and will not be seen by users. For example `mysite-internal.com`.
- Specify the following when creating the stack:
  - **Site Domain Name**: `hub.mysite.com`
  - **Site is Set Up On Route 53**: `Yes`
  - **Internal Domain**: `mysite-internal.com`
  - **Short Link Domain**: `myhub.link`
  - **Outgoing Email Domain**: `mysite.com`
  - **Outgoing Email Subdomain Prefix**: `mail`

### レシピ 4: Route 53 ではないドメイン

- You want to run your site on the top level domain `mysite.com`
- `mysite.com` is *not* registered on Route 53.
- You want short links on `myhub.link`

#### レシピ:

- Register and set up `myhub.link` on Route 53.
- Register and set up an *internal domain* on Route 53. This can be any name you want, and will not be seen by users. For example `mysite-internal.com`.
- Register and set up an *email domain* on Route 53. This will be used for outgoing email. If you have an existing email provider, you don't need a custom email domain and can specify your internal domain. For example `mysite-mail.com`.
- Specify the following when creating the stack:
  - **Site Domain Name**: `mysite.com`
  - **Site is Set Up On Route 53**: `No`
  - **Internal Domain**: `mysite-internal.com`
  - **Short Link Domain**: `myhub.link`
  - **Outgoing Email Domain**: `mysite-mail.com`
  - **Outgoing Email Subdomain Prefix**: `mail`
- Follow the steps around SSL certificates in [Using an Existing Domain](./hubs-cloud-aws-existing-domain.md)

### レシピ 5: Route 53管理下ではないサブドメイン

- You want to run your site on the top level domain `hub.mysite.com`
- `mysite.com` is *not* registered on Route 53.
- You want short links on `myhub.link`

#### レシピ:

- Register and set up `myhub.link` on Route 53.
- Register and set up an *internal domain* on Route 53. This can be any name you want, and will not be seen by users. For example `mysite-internal.com`.
- Register and set up an *email domain* on Route 53. This will be used for outgoing email. If you have an existing email provider, you don't need a custom email domain and can specify your internal domain. For example `mysite-mail.com`.
- Specify the following when creating the stack:
  - **Site Domain Name**: `hub.mysite.com`
  - **Site is Set Up On Route 53**: `No`
  - **Internal Domain**: `mysite-internal.com`
  - **Short Link Domain**: `myhub.link`
  - **Outgoing Email Domain**: `mysite-mail.com`
  - **Outgoing Email Subdomain Prefix**: `mail`
- Follow the steps around SSL certificates in [Using an Existing Domain](./hubs-cloud-aws-existing-domain.md)
