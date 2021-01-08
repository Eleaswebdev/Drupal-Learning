# Drupal-Learning

example link: https://drupal.stackexchange.com/questions/208201/how-to-get-each-field-value-in-views-views-unformatted-view-machine-name-html-t

I have found a Way using Kint, You can get field values in views-view--unformatted.html.twig

if you want a specific field

To get text fields value

{{row.content['#row']._entity.field machine name[0].value}}

To get image fields src

{{file_url(row.content['#row']._entity.field machine name.entity.uri.value)}}

To get image alt,title,width,height

{{row.content['#row']._entity.field machine name[0].alt/title/width/height}}

Note : replace field machine name with your fields machine name

If you Want to loop through multiple field

{% for i in range(0, 10) %}
  {{ row.content['#row']._entity.body[i].value }}
{% endfor %}
If you Want raw value

{% for i in range(0, 10) %}
  {{ row.content['#row']._entity.body[i].value|raw }}
{% endfor %}
