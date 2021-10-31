# Quick Start

Welcome to Dashy! So glad you're here 😊 In a couple of minutes, you'll have your new dashboard up and running 🚀

**TDLR;** Run `docker run -p 8080:80 lissy93/dashy`, then open `http://localhost:8080`

---

## 1. Prerequisites

The quickest and easiest method of running Dashy is using Docker (or another container engine). You can find installation instructions for your system in the [Docker Documentation](https://docs.docker.com/get-docker/).
If you don't want to use Docker, then you can use one of Dashy's other supported installation methods instead, all of which are outlined in the [Deployment Docs](https://github.com/Lissy93/dashy/blob/master/docs/Deployment.md).

---

## 2. Installation

To pull the latest image, and build and start the app run:
```
docker run -d \
  -p 8080:80 \
  --name my-dashboard \
  --restart=always \
  lissy93/dashy:latest
```

For a full list of available options, then see [Dashy with Docker](https://github.com/Lissy93/dashy/blob/master/docs/Deployment.md#deploy-with-docker) Docs. If you'd prefer to use Docker Compose, then see [Dashy with Docker Compose](https://github.com/Lissy93/dashy/blob/master/docs/Deployment.md#using-docker-compose) Docs.

Your dashboard should now be up and running at `http://localhost:8080` (or your servers IP address/ domain, and the port that you chose). The first build will may take a few minutes

---

## 3. Configure

Now that you've got Dashy running, you are going to want to set it up with your own content.
Config is written in [YAML Format](https://yaml.org/), and saved in [`/public/conf.yml`](https://github.com/Lissy93/dashy/blob/master/public/conf.yml).
The format on the config file is pretty straight forward. There are three root attributes:
- [`pageInfo`](https://github.com/Lissy93/dashy/blob/master/docs/Configuring.md#pageinfo) - Dashboard meta data, like title, description, nav bar links and footer text
- [`appConfig`](https://github.com/Lissy93/dashy/blob/master/docs/Configuring.md#appconfig-optional) - Dashboard settings, like themes, Authentication, language and customization
- [`sections`](https://github.com/Lissy93/dashy/blob/master/docs/Configuring.md#section) - An array of sections, each including an array of items


You can view a full list of all available config options in the [Configuring Docs](https://github.com/Lissy93/dashy/blob/master/docs/Configuring.md).

```yaml
pageInfo:
  title: Home Lab
sections: # An array of sections
- name: Example Section
  icon: far fa-rocket
  items:
  - title: GitHub
    description: Dashy source code and docs
    icon: fab fa-github
    url: https://github.com/Lissy93/dashy
  - title: Issues
    description: View open issues, or raise a new one
    icon: fas fa-bug
    url: https://github.com/Lissy93/dashy/issues
- name: Local Services
  items:
  - title: Firewall
    icon: favicon
    url: http://192.168.1.1/
  - title: Game Server
    icon: https://i.ibb.co/710B3Yc/space-invader-x256.png
    url: http://192.168.130.1/
```

Notes:
- You can use a Docker volume to pass a config file from your host system to the container
  - E.g. `-v ./host-system/my-local-conf.yml:/app/public/conf.yml`
- It's also possible to edit your config directly through the UI, and changes will be saved in this file
- Check your config against Dashy's schema, with `docker exec -it [container-id] yarn validate-config`
- You might find it helpful to look at some examples, a collection of which can be [found here](https://gist.github.com/Lissy93/000f712a5ce98f212817d20bc16bab10)
- After editing your config, the app will rebuild in the background, which may take a minute

---

## 4. Further Customisation

Once you've got Dashy setup, you'll want to ensure the container is properly healthy, secured, backed up and kept up-to-date. All this is covered in the [Management Docs](https://github.com/Lissy93/dashy/blob/master/docs/Management.md).


You might also want to check out the docs for specific features you'd like to use:
- [Authentication](/docs/Authentication.md) - Setting up Authentication to protect your dashboard
- [Backup & Restore](/docs/backup-restore.md) - Guide to Dashy's cloud sync feature
- [Icons](/docs/icons.md) - Outline of all available icon types for sections and items
- [Localisation](/docs/Internationalization.md) - How to change language, or add your own
- [Status Indicators](/docs/Status-Indicators.md) - Using Dashy to monitor uptime and status of your apps
- [Theming](/docs/theming.md) - Complete guide to applying, writing and modifying themes and styles

---

## 5. Final Note

If you're enjoying Dashy, and have a few minutes to spare, please do take a moment to look at the [Contributing Page](https://github.com/Lissy93/dashy/blob/master/docs/Contributing.md). There are a few things that we really need some help with, and whatever your skill set, there are ways you can help out. Any contributions, however small would be greatly appreciated.
Thank you to [everyone](https://github.com/Lissy93/dashy/blob/master/docs/Credits.md) who is already doing so, without developing and maintaining Dashy would not have been so possible.

You can also consider sharing your dashboard in the [Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Showcase---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------](https://github.com/Lissy93/dashy/blob/master/docs/Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Dashy-Showcase---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------.md), to help provide inspiration for others.

For more info, check out the [Documentation](https://github.com/Lissy93/dashy/tree/master/docs#readme). If you've got any questions feel free to ask in the [Discussion](https://github.com/Lissy93/dashy/discussions), and if you think you've found a bug you can [raise an issue](https://github.com/Lissy93/dashy/issues/new/choose) to get it fixed.

Enjoy your dashboard :) 

---
