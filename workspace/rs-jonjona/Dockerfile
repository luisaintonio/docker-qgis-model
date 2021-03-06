# Copyright 2016 Daniel Nüst
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
FROM nuest/qgis-model:xenial-multimodel
MAINTAINER Daniel Nüst <daniel.nuest@uni-muenster.de>

COPY . /workspace

# Default options must be set in model.py, the values are duplicated here to fill the options table in Kitematic 
LABEL de.ifgi.qgis-model.options '[ \
    { "id": "settlement_threshold", \
      "name": "settlement detection sensitivity", \
      "value": "0.3", \
      "comment": "the standard deviation that an image segment/image object is used as a seed for a settlement" }, \
    { "id": "settlement_size", \
      "name": "minimum settlement size", \
      "value": "0", \
      "comment": "the minimal size for a settlement candidate after grow and merge of seeds (unit: m²)" }, \
    { "id": "change_analysis_threshold", \
      "name": "change sensitivity", \
      "value": "0.33", \
      "comment": "minimum change in edge intensity for objects to be flagged as changed" }]'

# Execute the following commands _in the directory of this file_ to build and execute a self-contained image:
# BUILD COMMAND: docker build -t qgis-model-rs-jonjona --no-cache .
# RUN COMMAND: docker run --name rs-jonjona -it qgis-model-rs-jonjona
# Extract results: docker cp rs-jonjona:/results .
# RUN with changed parameters:
#   docker run --name rs-jonjona-params -e "change_analysis_threshold=0.2" qgis-model-rs-jonjona