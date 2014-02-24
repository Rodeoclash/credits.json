# credits.json

Machine readable data format that describes the creators of a website.

### Isn't this humans.txt?

Humans.txt is great but it's not machine parsable[0], in fact being machine parsable would almost defeat the purpose of humans.txt. credits.json is similar in the sense that it provides information about who built the site but the key difference is that it's in a strict format which is easily machine parsable.

[0]: Just have a look at the differences between [Google's](https://www.google.com/humans.txt) and [Github's](https://www.github.com/humans.txt) humans.txt files.

### Ok, but why?

* It proves that a person worked on a particular website, along with what they did to help produce.
* It makes it possible to write tools that can analyse who worked on a site and which other sites they worked on.
* It gives recognition to the builders of a site.

### Who's making this?

We've[0] started designing the format but we want everyone who produces websites to be involved. Part of the problem with the original humans.txt is that it was created by just one person and this has introduced limitations into the format. We want to avoid this by gathering as much feedback as possible and incorporating it into the formaat.

If you want to get involved, please fork the project, make your changes then submit a pull request for discussion.

We want this format to be as open as possible so we've picked the Apache License, however if you feel this isn't a good choice, we are happy to change this.

[0]: [Sam](https://github.com/Rodeoclash) and [Riley](https://github.com/rjaus)

## The Format

#### Version

```
{
  version: "0.1"
}
```

The credits.json format is versioned so we can handle changes to the format without breaking previous releases. Version 1.0 will be the first public release with point releases afterwards to deal with omissions. Major releases (e.g. 2.0) are reserved for format breaking changes.

#### Created at

```
{
  created_at: "2014-02-22"
}
```

The date the credits.json file was created. This is used for tracking snapshots of the site over time.

#### Person
This node represents a person or multiple people involved in the project and is present as an array in the root of the format.

```
{
  id: "$2a$10$JGDDOBPPnuUiwb/OSHL4du9NwbHb/ZygFJm/SXk/wl1b9NoxlHQAO",
  name: "John Doe",
  roles: ['Design', 'Front end development'],
  location: "123 Street, My City, A Country",
  more: {
    twitter: "@handle",
    stack_overflow: "stackoverflow.com/users/151433/samuel",
    homepage: "http://www.example.com"
  }
}
```

Let's take a closer look at the fields under a person:

| Field        | Description   |
| :------------|:--------------|
| id           | This is a bcrypt hash of the persons email address. It's used to track a person working over multiple sites. |
| name         | The persons name or alias. |
| location     | A specific or non specific location of where the work on the site was performed. |
| more         | Further details about the user that can be found around the internet. |

People can also work on a site via an organisation, see below for more details.

#### Organisations

```
{
  name: "The Super Design Agency",
  location: "123 Street, My City, A Country",
  homepage: "http://www.example.com",
}
```

Two top level entities are allowed in the format, the first of which is Organisations. This represents business like entities that worked on the site for the [client](#client).

#### Client <a name="client"></a>

### Putting it all together
```
{
  version: "0.1",
  created_at: "2014-02-22",
  client: {
    client: "todo"
  },
  organisations: [
    {
      name: "The Super Design Agency",
      location: "123 Street, My City, A Country",
      homepage: "http://www.example.com",
      people: [
        {
          name: "John Doe",
          id: "$2a$10$JGDDOBPPnuUiwb/OSHL4du9NwbHb/ZygFJm/SXk/wl1b9NoxlHQAO",
          roles: ['Design', 'Front end development'],
          location: "123 Street, My City, A Country",
          homepage: "http://www.example.com"
        }
      ]
    }
  ],
  people: [
    {
      name: "Jane Doe",
      id: "$2a$10$Rs2//C.zRkfYeXiZwp.vuutbkKV6mxR5Xnpo8D/oShsrj9VTIf/Mm",
      roles: ['Backend end development'],
      location: "123 Street, My City, A Country",
      homepage: "http://www.example.com"
    }
  ]
}
```

#### Other resources

* credits.json generator coming soon

#### Changelog

* First version