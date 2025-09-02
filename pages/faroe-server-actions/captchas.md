---
title: "Captchas"
---

# Captchas

Faroe does not support Captchas natively.

Instead, treat Captchas as part of the action invocation endpoint's authentication by sending the Captcha token in the request header.

```
X-Captcha-Token: xxx
```

Create 2 action invocation endpoints, one that requires Captcha and one that doesn't. Make sure that the endpoint that doesn't require Captcha can't invoke critical actions.

```
POST /invoke-action
POST /invoke-action-with-captcha
```
