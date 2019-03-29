# Uptime kafka producer

This project sends the host's `uptime` data to a kafka server.

## Install

Install the script in a virtualenv:

    pip3 install git+https://github.com/fmorato/uptime-producer.git

Run from a terminal or use a supervisor such as `systemd` or `supervisord`.

    producer --ca /path/to/ca \
            --cert /path/to/cert \
            --key /path/to/key \
            --client-id CLIENT_ID \
            --topic TOPIC \
            --kafka KAFKA_URL

The certificate files can be left out for plaintext connection.

## Development

Clone the repository from github:

    git clone https://github.com/fmorato/uptime-producer.git
    cd uptime-producer
    mkvirtualenv -a . -p python3 uptime-producer  # requires virtualenvwrapper
    pip install -e .

Start the producer.

    producer --topic TOPIC --kafka KAFKA_URL
