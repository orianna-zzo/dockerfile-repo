# dockerfile-repo

## front-end-docker
Docker for Front End Development:

### Sass-docker
Sass compiler:
* [Sassc](libsass-docker) -> libsass (lack some functions)
* [Dart sass](dart-sass-docker) (based on node.js)

The differences are: 

|                           | Libsass Docker | Dart Sass Docker |
| ------------------------- | -------------- | ---------------- |
| **Size**                  | 8.76MB         | 680MB            |
| **Writen in**             | C              | JS               |
| **Compiling Speed**       | Fast           | Normal           |
| **Integrated with JS**    | No             | Yes              |
| **Function**              | Limited        | Full             |
| **Update Feq & Priority** | Normal         | First Priority   |
