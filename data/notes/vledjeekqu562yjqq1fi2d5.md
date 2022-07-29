

## Anchors

```yaml
man:
  name: Utibe
  age: 1000
  galaxy: milky-way
  dinosaursExist: no
alien:
  name: kal-el
  age: 10000000
  galaxy: milky-way
  dinosaursExist: no
names:
  - Utibe
  - kal-el
```

> As you can see, we have a names key that lists the `names` of both `man` and `alien`.
> However, this is not ideal as we are writing out the names multiple times and if the name changes we have to change each reference to it.
> YAML has a feature known as anchors that allows us to reference a value. Here’s how it works

```yaml
man:
  name: &man Utibe
  age: 1000
  galaxy: milky-way
  dinosaursExist: no
alien:
  name: &alien kal-el
  age: 10000000
  galaxy: milky-way
  dinosaursExist: no
names:
  - *man
  - *alien
```

### Remove Redundancy With Anchors

```yaml
metadata: &metadata
  galaxy: milky-way
  dinosaursExist: no
man:
  name: &man Utibe
  age: 1000
  <<: *metadata
alien:
  name: &alien kal-el
  age: 10000000
  <<: *metadata
names:
  - *man
  - *alien
```

And to overide standard template metadata in this example with specific values simply overwrite at the end as if the last thing read is what happens like in [[s.m.css]]

```yaml
man:
  name: &man Utibe
  age: 1000
  <<: *metadata
  galaxy: another-galaxy
```
