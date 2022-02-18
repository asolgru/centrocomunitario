---
title: Home
layout: base
---


<section class="events">
    <div class="container">
        <div class="row">
            <h2 class="text-center white-text biko">Eventos</h2>
            {% assign sorted = site.data.events %}
            {% for event in sorted %}               
                <div class="col-sm-6 col-md-4 ">
                    <a {% unless event.url == null %} href="{{event.url}}" {% endunless %} target="_blank" class="event-url">
                        <div class="panel panel-default ">
                            <div class="panel-heading">
                                <span class="past-text biko">Eventos Passados</span>
                                {% if event.image-url %}<img class="img-responsive {% unless event.light_background == null %}light_background{% endunless %}" src="{{event.image-url}}">{%endif%}
                                <h4 class="biko {% unless event.light_background == null %}light_background{% endunless %}" >{{event.name}}</h4>
                            </div>
                            <div class="panel-body event" data-date="{{ event.date }}">                                
                                <p>{{event.line}}</p>
                            </div>
                            <div class="panel-footer">
                                {{event.date |  date: "%d/%m/%y" }}{% unless event.location == null or event.date == null  %}, {% endunless %} {{event.location}}
                            </div>
                        </div>
                    </a>
                </div>
            {% endfor %}
        </div>
        <div class="row text-center">
            	<a class="btn btn-accent btn-block" href="https://calendar.google.com/calendar/u/1?cid=cXM5c2doNHJwb3VhYjRwYmozN3VpcTBuOW9AZ3JvdXAuY2FsZW5kYXIuZ29vZ2xlLmNvbQ" target="_blank"><i class="fa fa-calendar" aria-hidden="true"></i>Adicione no Google Agenda</a>
        </div>
    </div>
</section>
