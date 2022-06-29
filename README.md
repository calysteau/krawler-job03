# krawler-job03

 Download Meteo France Radar imagery using __Kalisio Krawler__ https://github.com/kalisio/krawler
 
 This sample is based on https://github.com/kalisio/k-meteoradar, adapted to run on Windows for development and training purpose

## Setting up the environment

### git install
Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

Download and install : https://git-scm.com

### nvm install
nvm is a version manager for node.js, designed to be installed per-user, and invoked per-shell.

Download and install : https://github.com/coreybutler/nvm-windows

Then install Node 16

```bash
nvm install 16
nvm use 16.15.1
```

### yarn install
Yarn is a package manager that doubles down as project manager.

Download and install : https://classic.yarnpkg.com/lang/en/docs/install/#windows-stable

Add yarn to Windows environment PATH variable

### GDAL install
GDAL is a translator library for raster and vector geospatial data formats

Download and install GDAL from https://trac.osgeo.org/osgeo4w/ (or install QGIS https://www.qgis.org/ that contains GDAL)

Set windows environment variables for GDAL according to your GDAL installation

```bash
set PATH=%PATH%;c:\Program Files\QGIS 3.24.0\bin
```

### Rclone install
Rclone is a command-line program to manage and transfer files on local or cloud storage.

Download and install Rclone from https://downloads.rclone.org/v1.58.1/rclone-v1.58.1-windows-amd64.zip

Add rclone to Windows environment PATH variable

Use rclone config to set your store (according your needs, S3, FTP, local ...)

```bash
rclone config
```
NB : In this sample, we use a local store

## Krawler install
Krawler is a minimalist ETL that make automated process of extracting and processing (geographic) data from heterogeneous sources with ease

In the working directory (e.g. c:\workspace), create a kalisio directory

```bash
cd c:\workspace\kalisio
git clone https://github.com/kalisio/krawler
cd krawler
yarn install
yarn link
```

## job03 install
In the kalisio directory ( ex: C:\workspace\kalisio)

```bash
git clone https://github.com/calysteau/krawler-job03
cd krawler-job03
yarn install
yarn link @kalisio/krawler
```

Run the job
```bash
krawler jobfile.js
```

## Notes

If you need to activate the Krawler DEBUG

```bash
set DEBUG= krawler*   (pour CMD)
```
or 
```bash
$env:DEBUG="krawler*"  (pour PowerShell)
```
