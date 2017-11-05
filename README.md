## Rails Girls Recife 2016

Esse projeto foi elaborado em equipe (eu & [@yankasantos](https://github.com/yankasantos)) no evento Rails Girls Recife, em 19/11/2016.
Para mais informações sobre o evento acesse o link: http://railsgirls.com/


<b> Materiais: </b> 
Tutorial: http://www.maujor.com/railsgirlsguide/

### Configuração do ambiente:
  
Uso a distribuição Antergos, baseada no Arch Linux, então segui com um tutorial de instalação para Linux. Instalei o Ruby, sqlite3 e o Rails, mas nesse parte recebo a seguinte mensagem do terminal:
```
[user@hostname]: ~>$ gem install rails
WARNING:  You don't have /home/user/.gem/ruby/2.4.0/bin in your PATH,
	  gem executables will not run.
Successfully installed rails-5.0.0
...
```
O Rails foi instalado com sucesso, mas eu não tinha o caminho `/home/user/.gem/ruby/2.4.0/bin` adcionado na variável de ambiente PATH. E qual o problema? É que quando tentanva *chamar* o Rails o sistema não o encontra. Veja o que acontecia quando eu tentava verificar a versão:
```
[user@hostname]: ~>$ rails --version
bash: rails: comando não encontrado
```
Ou quando tentava verificar a localização:
```
[user@hostname]: ~>$ which rails
which: no rails in (/usr/local/sbin:/usr/local/bin:/usr/bin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl)
```

Para resolver isso é bem simples, basta fazer o que o sistema já sugeriu: adicionar o caminho na variável de ambiente PATH. Registrei o caminho nos arquivos `.bash_profile` e `.bashrc` que se encontram no ambiente local.
```js
export PATH=$PATH:/home/user/.gem/ruby/2.4.0/bin/
```

Pronto! Agora o sistema já encontra o caminho do Rails.
```
[user@hostname]: ~>$ which rails
/home/mayra/.gem/ruby/2.4.0/bin/rails
[user@hostname]: ~>$ rails --version
Rails 5.0.0

```

É importante saber que o Rails Girls também disponibiliza um script de instalação para várias distribuições, inclusive para Arch Linux. Segue link dos códigos no GitHub: https://github.com/railsgirls/installation-scripts.
