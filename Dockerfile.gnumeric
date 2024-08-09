FROM continuumio/anaconda3:4.4.0

COPY . /usr/app/
WORKDIR /usr/app/

# Update the base environment
RUN conda update -n base -c defaults conda

# Create a new environment with the latest versions of required packages
RUN conda create -n myenv python=3.8
RUN echo "conda activate myenv" >> ~/.bashrc
ENV PATH /opt/conda/envs/myenv/bin:$PATH

# Copy requirements.txt before installing dependencies
COPY requirements.txt .

# Install the required packages
RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 5000

CMD ["python", "app.py"]
