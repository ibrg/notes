# Best practices
### Создания поста

```
if request.method == 'POST':
	data = { 
		'title': request.POST['title'], 
		'author': request.POST['author'] 
	} 
	Article.objects.create(**data).save() 
articles = Article.objects.all()
```

# Полезные ссылки
[Python: конфигурация проекта без боли](https://habr.com/ru/post/575094/)