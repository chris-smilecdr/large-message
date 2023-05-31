# Use base Smile CDR image as parent image
FROM smilecdr:2023.05.R01

# Set the smilecdr folder as working directory
WORKDIR /home/smile/smilecdr

# Copy modified properties file to the container.
copy ./cdr-config-Master.properties ./classes/cdr-config-Master.properties

