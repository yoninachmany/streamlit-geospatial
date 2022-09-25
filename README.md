# Chips

## Team Members

Ishaan Jhaveri: <https://ishaanjhaveri.com>
[GitHub](http://github.com/iaj8) | [Twitter](https://twitter.com/ishaan_jhavs) | [LinkedIn](https://www.linkedin.com/in/iajhaveri)

Yoni Nachmany: <https://www.yoninachmany.com>
[GitHub](https://github.com/YoniNachmany) | [Twitter](https://twitter.com/YoniNachmany) | [LinkedIn](https://www.linkedin.com/in/YoniNachmany/)

## Tool Description

To our knowledge, there is no existing browser-based tool to easily upload a dataset with locations, crop satellite images for all those locations, download the images locally, and visualize them on a website.

Large geospatial datasets, like those of [US prisons](http://prisonmap.com/) or [permitted natural gas wells in West Virginia](https://projects.propublica.org/graphics/wva-well-pads), can illuminate patterns or surface anomalies when viewed with satellite imagery. [Earlier](https://studioforcreativeinquiry.org/project/terrapattern) [projects](https://search.descarteslabs.com/) have tried to leverage the visual similarity of aerial images for pattern recognition. Given a dataset with coordinates, can we accelerate the downloading and previewing of satellite images for those places to drive insights and facilitate downstream tasks such as labeling data or producing reports?

[Buzzfeed](https://www.buzzfeednews.com/article/alison_killing/satellite-images-investigation-xinjiang-detention-camps) scraped and filtered millions of map images to identify hundreds of prisons and internment camps in Xinjiang, with significant manual effort. We are interested in making such workflows more accessible by allowing users to drop in a file with points or draw their own points and select options for downloading satellite and aerial images, which are displayed on a site and can feed both human analysis and machine learning models.

## Installation

Our tool is derived from https://github.com/giswqs/streamlit-geospatial – the code and [related blog post](https://blog.streamlit.io/creating-satellite-timelapse-with-streamlit-and-earth-engine/) should serve as references for installation.

1. Make sure you have Python version 3.8 or greater installed

2. Download the tool's repository:

        git clone https://github.com/yoninachmany/streamlit-geospatial.git

3. Download [Anaconda](https://www.anaconda.com/distribution/#download-section) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html) to create and activate a new environment with the required packages:

        conda env create -f environment-bk.yml
        conda activate geo

4. [Sign up](https://earthengine.google.com/signup/) for a [Google Earth Engine](https://earthengine.google.com/) account and get a token by starting Python in the terminal and running the following commands ([more instructions](https://blog.streamlit.io/creating-satellite-timelapse-with-streamlit-and-earth-engine/#4-get-an-earth-engine-token)):

		import ee
		ee.Authenticate()

5. Run the [Streamlit](https://streamlit.io/) app:

		streamlit run streamlit_app.py

5. Deploy the app to [Streamlit Cloud](https://share.streamlit.io/) ([more instructions](https://blog.streamlit.io/creating-satellite-timelapse-with-streamlit-and-earth-engine/#5-deploy-your-app-to-streamlit-cloud))

## Usage

Watch [this video](https://www.youtube.com/watch?v=VVRK_-dEjR4) for an overview of how to use a similar tool with related workflows. Instructions and hints are documented throughout the site.

A typical workflow is to upload a GeoJSON/KML/zipped shapefile with points, customize chip parameters, and then click the Submit button to start downloading images and displaying them on the site.

## Additional Information

Potential next steps for the tool include:

- Manually entering coordinates to lower the barrier to entry for uploading data
- Selecting images by date ranges and aggregating images in a time period
- Modifying the size and shape of image crops (adding a circular crop option)
- Interacting with images (selecting, copying, removing images)
- Increasing performance of image downloading
- Including links to images for faster downloading

Our tool is limited to working with data in Google Earth Engine, not commercial map providers. In addition, we have not fully tested the edge cases of our satellite imagery queries or tried optimizing for speed.

The app was built using [streamlit](https://streamlit.io), [geemap](https://geemap.org), and [Google Earth Engine](https://earthengine.google.com). As Python developers, we could build a data-dependent application more quickly with Streamlit, especially combined with Google Earth Engine's vast imagery collection.
