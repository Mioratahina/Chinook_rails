# Chinook_rails

# NIVEAU FACILE
# le nombre total d'objets Album contenus dans la base
Album.count
	=> 307

# l'auteur de la chanson "White Room"
Track.find_by(title: "White Room")
	=> Eric Clapton

#chanson qui dure exactement 188133 milliseconds
Track.find_by(duration: 188133)
	=> Perfect

#groupe qui a sorti l'album "Use Your Illusion II"
Album.find_by(title: "Use Your Illusion II")
	=> Gun N Roses


# NIVEAU MOYEN
#Nombre d'album dont le titre contient "Great"
a = Album.where("title like ?", "%Great%")
a.count
	=> 13

#Suppression de tous les albums dont le nom contient "music"
b = Album.where("title like ?", "%music%")
b.destroy_all 

#Nombre d'albums écrit par AC/DC
c = Album.where("artist like ?", "%AC/DC%")
c.count
	=> 2


#Nombre de chonson qui durent exactement 158589 Millisecondes
Track.find_by(duration: 158589)
	=> 0


#NIVEAU DIFFICILE
# puts en console tous les titres de AC/DC.
c.each do |i|
	puts i.title
end
	=>	For Those About To Rock We Salute You
		Let There Be Rock

# puts en console tous les titres de l'album "Let There Be Rock".
d = Track.where("album like ?", "Let There Be Rock")
d.each do |i|
	puts i.title
end
	=>	Go Down
		Dog Eat Dog
		Let There Be Rock
		Bad Boy Boogie
		Problem Child
		Overdose
		Hell Aint A Bad Place To Be
		Whole Lotta Rosie

# le prix total de cet album ainsi que sa durée totale.
total_price = 0
total_duration = 0
d.each do |i|
	total_price += i.price
	total_duration += i.duration
end
	=> total_price = 7.920000000000001
	=> total_duration = 2453259

#Le cout de l'integralité de la discographie de "Dee Purple"
d = Track.where(artist: "Deep Purple")
total_price_deep = 0
e.each do |i|
	total_price += i.price
	total_duration += i.duration
end
	=> total_price_deep = 90.0899999999999

#Affichage de tous les titres de 'Eric Clapton' avec 'Britney Spears' en artist
f = Track.where(artist: "Eric Clapton")
f.each do |i|
	i.artist = "Britney Spears"
end
	=> artist = "Britney Spears"