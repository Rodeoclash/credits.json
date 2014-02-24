# credits.json

Machine readable data format that describes the creators of a website.

### Isn't this humans.txt?

Not quite. Humans.txt is a great effort but it's not easily machine parsable[^different-humans-txt], in fact, being machine parsable would almost defeat the purpose of humans.txt.

[^different-humans-txt]: Just have a look at the differences between [Google's](https://www.google.com/humans.txt), [Github's](https://www.github.com/humans.txt) and [humanstxt.org's](http://humanstxt.org/humans.txt)

### Ok, but why?

With a credits.json file it makes it easy to track what websites you've built over the internet, not only that, you can prove you worked on the site because the credits.json actually exists on the site that you build. Once the credits.json is in place, it's easy to automatically pull information from it. This makes it easy to generate portfolio websites and build a history of the work you've done.

### Who's making this?

At the moment it's just two of us but the purpose of creating this repository is to get input from everyone on what the credits.json format should include. If you've got some ideas or suggestions, please fork, implement and make a pull request so everyone can discuss the changes. As well as an open discussion that will shape the format, it is also licensed using the Apache License.

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

This node represents a person or multiple people involved in the project. People can work directly on a project or via an organisation. Let's take a closer look at the fields under a person:

| Field        | Description   |
| :-----------:|:-------------:|
| id           | This is a bcrypt hash of the persons email address. It's used to track a person working over multiple sites. |
| name         | The persons name or alias. |
| location     | A specific or non specific location of where the work on the site was performed. |
| more         | Further details about the user that can be found around the internet. |

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

#### The full format
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

### More resources

* credits.json generator coming soon
