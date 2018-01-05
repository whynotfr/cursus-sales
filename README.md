# Mise en ligne des ressources dans un format lisible
Dans ce dossier, nous pourrons retrouver les différentes `lessons` et `projects` des parcours de The Hacking Project.

## Organisation
Voici comment le truc va être :

```
|-- thp
    |-- README.md
    |-- code
    |   |-- lessons
    |   |   |-- 01-01-a.html
    |   |-- projects
    |       |-- 01-02-a.html
    |-- sales
    |   |-- lessons
    |   |   |-- 01-01-a.html
    |   |-- projects
    |   |   |-- 01-01-a.html
```

Le fichier `README.md` est celui-ci : il contient toutes les infos importantes. Puis pour chaque cursus a son sous-dossier. Enfin, chaque cursus contiendra un dossier pour les `lessons`, et un dossier pour les `projects`.


Enfin, dans les dossier, il y aura les fichiers contenant la ressource, au format HTML. Dans ce dossier nous ne trouverons ni le `title`, ni la `short_presentation` de la ressource. Cette dernière est facile à gérer dans le fichier spreadsheet.

### Les noms des fichiers
Chaque fichier aura le nom suivant :
```
[week_position]-[day_position]-[letter].html
```

* La `week_position` correspond au numéro de la semaine concernée
* La `day_position` correspond au numéro du jour concerné
* La `letter` correspond à la position de la ressource concernée dans le jour

Ainsi, la première leçon du mardi de la semaine 3 du parcours code aura comme path :
```
code/lessons/03-02-a.html
```

Le deuxième projet du vendredi de la première semaine du parcours sales aura comme path :
```
sales/projects/01-05-b.html
```


## Fichiers spreadsheets

* Voici [le lien du fichier spreadsheet contenant le programme de Sales](https://docs.google.com/spreadsheets/d/12zatlD809Ghklab2zylPTjUjMqiyeBBgoYnRLBhyIDc/edit?usp=sharing)
* Voici [le lien du fichier spreadsheet contenant le programme de Code](https://docs.google.com/spreadsheets/d/1KjMnU7oB8-J6lt49wLlxB05VHCyNumF4bsalyfkMdR4/edit?usp=sharing)

## Le format des HTML
Afin de garder une certaine consistance, il est très important de respecter les guidelines suivantes. Voici donc une certaine structure à garder pour les fichiers. Les fichiers seront balancés dans un erb que voici :

```erb
<% @selected_day.lessons.each do |lesson| %>
    <h3><%= lesson.title %></h3>
    <p><%= lesson.short_presentation %></p>
    <%= raw lesson.content %>
<% end %>
```

Donc le titre de la ressource est envoyé, ainsi que la `short_presentation`, qui servira de résumé. Voici un exemple de projet :



```html
<h4>1. Titre 1</h4>
<h5>1.1. Sous-titre 1</h5>
<p>Blabla bla</p>

<ul class="ul-normal">
	<li>Faire ceci</li>
	<li>Faire cela</li>
	<li>Lire <a href="url" target="_blank" class="text-primary">ce truc</a></li>
</ul>

<h5>1.2. Sous-titre 2</h5>

<blockquote class="blockquote">
Une citation stylay
</blockquote>

<pre>&gt; code_writer("trop bien !")
=&gt; "Deuxième ligne trop bien !"
</pre>

<h4>2. Titre 2</h4>
<p>Et tu peux aussi mettre un bout en rouge avec ceci : <code>ligne_rouge</code></p>
```

### Exemples
```html
<blockquote class="blockquote">Citation</blockquote>
```

Donne ceci :

> Citation

```html
<pre>$ du_code.code
donne ceci</pre>
```

```
$ du_code.code
donne ceci
```

```
<p>Enfin, on peut mettre du texte <code>en rouge avec ceci</code>.
```


Enfin, on peut mettre du texte `en rouge` avec <code>ceci</code>.



### Classes à donner


* Liens : 
* Listes : 