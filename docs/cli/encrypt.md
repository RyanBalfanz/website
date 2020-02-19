# Encryption

## `keys encrypt`

Encrypt text to armored msg.enc (from stdin).

```shell
echo -n "My secret 🤓" |  keys encrypt -armor \
-signer kex1mnseg28xu6g3j4wur7hqwk8ag3fu3pmr2t5lync26xmgff0dtryqupf80c \
-recipient kex1ts0qw8fwkvle2f2xsqumetmr9ev5ppx22rl5hnycen68sanjzl7qnta629 \
-recipient kex1mnseg28xu6g3j4wur7hqwk8ag3fu3pmr2t5lync26xmgff0dtryqupf80c > msg.enc
```

Encrypt image.png to image.png.enc (using -in and -out).

```shell
keys encrypt \
-signer kex1mnseg28xu6g3j4wur7hqwk8ag3fu3pmr2t5lync26xmgff0dtryqupf80c \
-recipient kex1ts0qw8fwkvle2f2xsqumetmr9ev5ppx22rl5hnycen68sanjzl7qnta629 \
-recipient kex1mnseg28xu6g3j4wur7hqwk8ag3fu3pmr2t5lync26xmgff0dtryqupf80c \
-in image.png -out image.png.enc
```

Encrypt image.png to image.png.enc (using stdin and stdout).

```shell
cat image.png | keys encrypt \
-signer kex1mnseg28xu6g3j4wur7hqwk8ag3fu3pmr2t5lync26xmgff0dtryqupf80c \
-recipient kex1ts0qw8fwkvle2f2xsqumetmr9ev5ppx22rl5hnycen68sanjzl7qnta629 \
-recipient kex1mnseg28xu6g3j4wur7hqwk8ag3fu3pmr2t5lync26xmgff0dtryqupf80c > image.png.enc
```

## `keys decrypt`

Decrypt from (from stdin).

```shell
cat msg.enc | keys decrypt -armor

verified kex1mnseg28xu6g3j4wur7hqwk8ag3fu3pmr2t5lync26xmgff0dtryqupf80c gabriel@github
My secret 🤓
```

Decrypt image.png.enc to image.png.

```shell
keys decrypt -in image.png.enc -out image.png

verified kex1mnseg28xu6g3j4wur7hqwk8ag3fu3pmr2t5lync26xmgff0dtryqupf80c gabriel@github
```