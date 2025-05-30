# Introduction

Each server does need a server profile. Instead of making a lot of the same server profile, you create a server template and derive this template multiple times.
In a server profile template, vNIC and vHBA templates can be used.

Besides server profile templates, chassis and UCS domain templates are possible. These will not be handled in this lab.

Another way to have the same **server profile**, is to **clone** it. This has advantages and disadvantages. It is **not** the **best practice** to use clones, but because this is a lab, we want to show you what the limitations are.

One of the limitations is: **Pools cannot be cloned**. They will be created as new pools without any values in them.
Policies, Templates and Server Profiles can be cloned.

First you are going to **clone** a **server profile template** and then **make changes**. 
Once it is a server profile template that you can use, you are going to derive this template.

NOTE:

**Do NOT delete DO_NOT_USE Template Profile.**

**Do NOT delete or any server policy or vNIC policy without your -SRVx at the end, where x is your pod number.**