# La musique dans la peau
Récupére tous les albums
> SELECT * from albums;

Récupére tous les albums dont le titre contient "Great" (indice)
> SELECT * from albums where title like '%Great%';

Donner le nombre total d'albums contenus dans la base (sans regarder les id bien sûr)
> SELECT count(*) from albums;

Supprimer tous les albums dont le nom contient "music"
> SELECT * from albums where title not like '%music%';

Récupérer tous les albums écrits par AC/DC
> SELECT * from albums inner join artists on albums.ArtistId = artists.ArtistId where artists.Name = 'AC/DC';

Récupérer tous les titres des albums de AC/DC
> SELECT albums.Title from albums inner join artists on albums.ArtistId = artists.ArtistId where artists.Name = 'AC/DC';

Récupérer la liste des titres de l'album "Let There Be Rock"
> SELECT tracks.Name from albums natural join tracks where albums.Title = 'Let There Be Rock';

Afficher le prix de cet album ainsi que sa durée totale
> SELECT sum(tracks.UnitPrice) from albums natural join tracks where albums.Title = 'Let There Be Rock';

Afficher le coût de l'intégralité de la discographie de "Deep Purple"
> SELECT sum(tracks.UnitPrice) from albums natural join tracks join artists where artists.Name = 'Deep Purple';

Créer l'album de ton artiste favori en base, en renseignant correctement les trois tables albums, artists et tracks
> INSERT INTO artists(Name) VALUES ('Laylow');
> INSERT INTO albums(Title, ArtistId) VALUES ('Etrange histoire de Mr.Anderson', (SELECT ArtistId from artists where Name = 'Laylow'));
> INSERT INTO tracks(Name, MediaTypeId, Milliseconds, UnitPrice, AlbumId) VALUES ('Special', 1, 0, 0, (SELECT AlbumId from albums where Title = 'Etrange histoire de Mr.Anderson'));
