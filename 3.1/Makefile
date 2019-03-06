
nominatim:
	@docker build -t ferimer/nominatim:latest .

spain: nominatim
	@mkdir -p data
	@curl http://download.geofabrik.de/europe/spain-latest.osm.pbf > data/spain.osm.pbf
	@docker run -t -v `pwd`/data:/data ferimer/nominatim:latest sh /app/init.sh /data/spain.osm.pbf postgresdata 4
	@rm data/spain.osm.pbf

