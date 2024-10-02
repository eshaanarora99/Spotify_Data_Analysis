## Instructions for Using the Comprehensive Spotify Analysis Program

### 1. **Requirements**:
   - **Python version**: Make sure you have Python 3.x installed on your system.
   - **Spotify Data**: You’ll need to request your Spotify listening data, which comes in JSON format. To request this data:
     1. Log into your Spotify account.
     2. Go to [Spotify Privacy Settings](https://www.spotify.com/us/account/privacy/).
     3. Request your listening data, and Spotify will email you a link when it's ready to download.

### 2. **Required Libraries**:
   You’ll need the following Python libraries to run the program:
   - **`pandas`**: For data analysis.
   - **`matplotlib`**: For generating charts.
   - **`folium`**: For creating interactive maps.
   - **`geoip2`**: For geolocating IP addresses using the GeoLite2 database.

   You can install these using `pip`:
   ```bash
   pip install pandas matplotlib folium geoip2
   ```

### 3. **Download the GeoLite2 Database**:
   To geolocate the IP addresses, you need the **GeoLite2-City** database:
   1. Go to the [MaxMind GeoLite2 website](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data).
   2. Create a free MaxMind account (if you don't have one).
   3. Download the **GeoLite2-City** database in `.tar.gz` format.
   4. Extract the `GeoLite2-City.mmdb` file from the archive.

### 4. **Program Setup**:
   1. **Spotify Data**: Ensure the JSON files containing your Spotify listening data are downloaded and stored in a folder (e.g., `C:\Users\eshaa\Downloads\Spotify Extended Streaming History`).
   2. **GeoLite2 Database**: Make sure you have the `GeoLite2-City.mmdb` file extracted from the downloaded archive.

### 5. **Adjust File Paths**:
   In the script, modify the following variables to point to your specific file locations:
   ```python
   # Path to the Spotify data directory
   data_directory = r'C:\Users\eshaa\Downloads\Spotify Extended Streaming History'  # Change this to your directory

   # Path to the GeoLite2-City.mmdb file
   geoip_db_path = r'C:\Users\eshaa\Downloads\GeoLite2-City.mmdb'  # Change this to the location of your mmdb file
   ```

### 6. **Running the Program**:
   After adjusting the paths, you can run the program. Here's what it will do:
   
   - **Load Spotify Data**: It reads your Spotify JSON data and processes it into a `pandas` DataFrame.
   - **Basic Statistics**: Displays statistics like the total number of streams, total listening time in minutes, the most played track, and the most played artist.
   - **Visualize Data**:
     - **Monthly Streaming Activity**: Plots your listening time (in minutes) by month.
     - **Top Artists and Tracks**: Displays bar charts of your top 10 most played artists and tracks (in minutes).
   - **Geolocate Streams**: Uses the `geoip2` library and the **GeoLite2-City** database to geolocate IP addresses from the streams.
   - **Interactive Map**: Creates an interactive map of your streams based on IP geolocation and saves it as an HTML file (`spotify_streams_map.html`), which can be opened in any web browser.

### 7. **Expected Outputs**:
   - **Terminal Output**:
     - Basic statistics, such as the total number of streams and top tracks/artists.
     - Geolocated IP addresses and their corresponding country and city.
   - **Charts**:
     - Line graph of streaming activity over time (minutes).
     - Bar charts for the top artists and tracks played (in minutes).
   - **Map**:
     - An interactive map (`spotify_streams_map.html`) showing the location of streams based on IP addresses.

### 8. **Viewing the Map**:
   The program will generate and save an interactive map as an HTML file (`spotify_streams_map.html`). You can open this file in any web browser to explore your stream locations.

---

### Troubleshooting:
- **Missing Libraries**: If you encounter `ModuleNotFoundError`, ensure you have installed the necessary libraries using `pip`.
- **FileNotFoundError**: If the program can’t find your Spotify JSON files or the **GeoLite2-City.mmdb** file, make sure the paths are correct and that the files exist in those locations.
- **Missing Spotify Data**: Ensure you've requested and downloaded your Spotify data from the **Spotify Privacy Settings** page.
