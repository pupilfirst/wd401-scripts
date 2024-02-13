## Text

Collaborative translation tools are software platforms designed to facilitate the process of translating and localizing content, particularly in scenarios where multiple translators or contributors work together. These tools offer a range of features to streamline translation workflows, ensure consistency, and enable effective collaboration among translators and teams.

Few features for such a software includes:

- Centralized Platform:

  Translation management tools provide a centralized platform where all translation-related activities take place. This includes managing source content and translations

- Collaboration and User Roles:

  They allow multiple users to collaborate on translation projects. Different user roles, such as translators, reviewers, and project managers, can be defined to assign tasks and responsibilities.

- Invite Community Contributors:

  Encourage community contributors to join the translation effort. You can use the translation management tool's built-in invitation system or promote it on your project's website, blog, or social media channels.

- Version Control:

  They typically include version control and history tracking features, allowing users to monitor changes, revert to previous versions, and maintain an audit trail of translation work.

### Collaborative tools

#### GitHub

Probably the most simplest and straight forward method is to store the translation files in aGitHub repository. But the limitation, is to add a key, we will have to edit each and every translation file.

#### Traduora

[Traduora](https://traduora.co/) is an open source tool that can be used to manage translations. Getting started is as simple as the following (assuming you have docker, docker compose v2 installed):

```sh
git clone https://github.com/ever-co/ever-traduora
cd ever-traduora
docker compose -f docker-compose.demo.yaml up
```

[Traduora Reference](https://docs.traduora.co/docs/getting-started)
