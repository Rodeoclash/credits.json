# credits.json

A machine readable data format that describes the creators of a website.

### Isn't this humans.txt?

Humans.txt is is not designed to be machine parsable[0], if it was it would defeat its original purpose. credits.json is designed to sit alongside a humants.txt and provide the same information in a format that machines can understand.

[0]: Just have a look at the differences between [Google's](https://www.google.com/humans.txt) and [Github's](https://www.github.com/humans.txt) humans.txt files.

### Why?

It makes it possible to write tools that can automatically analyse and track who worked on websites across the Internet.

### Who's making this?

We've[0] started designing the format but we want more involvement from people that build websites. A good file format is only good if many of the use cases for it can be thought of and incorporated into it 

Please get involved by forking the project, making your changes then submitting a pull request for discussion.

We want this format to be as open as possible so we've picked the Apache License, however if you feel this isn't a good choice, we are open to discussion about it.

[0]: [Sam](https://github.com/Rodeoclash) and [Riley](https://github.com/rjaus)

## The Format

#### Version

```
{
  version: "0.1"
}
```

The credits.json format is versioned so we can handle changes to the format without breaking previous releases. Version 1.0 will be the first public release with point releases afterwards to handle omissions. Major releases (e.g. 2.0) are reserved for format breaking changes.

#### Created at

```
{
  created_at: "2014-02-22T23:45:37+00:00"
}
```

The date the credits.json file was created in ISO 8601 format.

#### People <a name="people"></a>
This node represents a person or multiple people involved in the project and is present as an array in the root of the format.

```
{
  id: "$2a$10$JGDDOBPPnuUiwb/OSHL4du9NwbHb/ZygFJm/SXk/wl1b9NoxlHQAO",
  name: "John Doe",
  roles: ['Design', 'Front end development'],
  location: "123 Street, My City, A Country",
  extras: {
    twitter: "@handle",
    stack_overflow: "stackoverflow.com/users/151433/samuel",
    homepage: "http://www.example.com"
  }
}
```

Let's take a closer look at the fields under a person. Required fields are marked with a *.

| Field        | Description   |
| :------------|:--------------|
| id           | This is a bcrypt hash of the persons email address. It's used to track a person working over multiple sites. |
| name*        | The persons name or alias. |
| location     | A specific or non specific location of where the work was performed. |
| extras       | [Extra details](#user_extras) about the user that are not directly related to the build on this domain. |

If a person worked on a website via an organisation, they can be listed as a person belonging to an organisation instead. See [organisations](#organisations).

##### User extras <a name="user_extras"></a>
These are additional details about a user not related to the build.

| Field           | Description   |
| :---------------|:--------------|
| homepage        | A fully qualified url to the homepage of the person or organisation. |
| twitter_handle  | The organisations name. |
| stackoverflow_id| The unique ID of your Stack Overflow profile. |

#### Organisations <a name="organisations"></a>
This node represents an organisation or multiple organisations involved in the project and is present as an array in the root of the format.

```
{
  id: "$2a$10$JGDDOBPPnuUiwb/OSHL4du9NwbHb/ZygFJm/SXk/wl1b9NoxlHQAO",
  name: "The Super Design Agency",
  location: "123 Street, My City, A Country",
  extras: {
    twitter: "@handle",
    stack_overflow: "stackoverflow.com/users/151433/samuel",
    homepage: "http://www.example.com"
  }
}
```

Let's take a closer look at the fields under an organisation. Required fields are marked with a *.

| Field        | Description   |
| :------------|:--------------|
| id           | This is a bcrypt hash of the organisations homepage. It's used to track an organisation working over multiple sites. |
| name*        | The organisations name. |
| location     | A specific or non specific location of where the work was performed. |
| extras       | [Extra details](#organisation_extras) about the organisation that are not directly related to the build on this domain. |

Organisations can also nest [people](#people) under them if that person performed the work when working for the organisation. Here is a simplified organisation that had two people working for them.

```
{
  name: "The Super Design Agency",
  people: [
    {
      id: "$2a$10$JGDDOBPPnuUiwb/OSHL4du9NwbHb/ZygFJm/SXk/wl1b9NoxlHQAO",
      name: "John Doe",
      roles: ['Design', 'Front end development'],
      location: "123 Street, My City, A Country",
      extras: {
        twitter: "@handle",
        stack_overflow: "stackoverflow.com/users/151433/samuel",
        homepage: "http://www.example.com"
      }
    },
    {
      id: "$2a$10$NteDK2.mFs3yxpJC2mMqfOdochI8N.wSqtvKtIXTVT3CrCkrTRk1.",
      name: "Jane Doe",
      roles: ['Back end development'],
      location: "123 Street, My City, A Country",
      extras: {
        twitter: "@handle",
        homepage: "http://www.example.com"
      }
    }
  ]
}
```

##### Organisation extras <a name="organisation_extras"></a>
These are additional details about an organisation not related to the build.

| Field           | Description   |
| :---------------|:--------------|
| homepage        | A fully qualified url to the homepage of the person or organisation. |
| twitter_handle  | The organisations name. |

### Putting it all together
This is an example of a complete credits.json file.
```
{
  organsiations: [
    {
      name: "The Super Design Agency",
      people: [
        {
          id: "$2a$10$JGDDOBPPnuUiwb/OSHL4du9NwbHb/ZygFJm/SXk/wl1b9NoxlHQAO",
          name: "John Doe",
          roles: ['Design', 'Front end development'],
          location: "123 Street, My City, A Country",
          extras: {
            twitter: "@handle",
            stack_overflow: "stackoverflow.com/users/151433/samuel",
            homepage: "http://www.example.com"
          }
        },
        {
          id: "$2a$10$NteDK2.mFs3yxpJC2mMqfOdochI8N.wSqtvKtIXTVT3CrCkrTRk1.",
          name: "Jane Doe",
          roles: ['Back end development'],
          location: "123 Street, My City, A Country",
          extras: {
            twitter: "@handle",
            homepage: "http://www.example.com"
          }
        }
      ]
    }
  ],
  client: {
    name: "The Comfy Bed Company",
    location: "123 Street, My City, A Country",
    extras: {
      twitter: "@handle"
    }
  }
}
```

#### Other resources

* credits.json generator coming soon

#### Changelog

* First version