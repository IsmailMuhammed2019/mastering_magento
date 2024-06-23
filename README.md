# Magento 2 Tutorial

Welcome to the Mastering Magento 2 Tutorial repository! This guide will help you set up, configure, and use Magento 2 for Developing frontend activities to use and develop best practices in delivering the best e-commerce websites. 

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Installation](#installation)
4. [Configuration](#configuration)
5. [Usage](#usage)
6. [Contributing](#contributing)
7. [Resources](#resources)
8. [License](#license)

## Introduction

Magento 2 is a powerful and flexible e-commerce platform used by businesses worldwide. This tutorial is designed to help you get started with Magento 2, covering everything from installation to configuration and basic usage.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- A web server (Apache or Nginx)
- PHP 7.4 or higher
- MySQL 5.7 or higher
- Composer
- Git

## Installation

Follow these steps to install Magento 2:

1. **Clone the Repository**:
   ```sh
   git clone https://github.com/yourusername/magento-tutorial.git
   cd magento-tutorial
   ```

2. **Install Composer Dependencies**:
   ```sh
   composer install
   ```

3. **Set Up Environment**:
   - Create a `.env` file from the example:
     ```sh
     cp .env.example .env
     ```

4. **Install Magento**:
   ```sh
   bin/magento setup:install \
   --base-url=http://yourdomain.com/ \
   --db-host=localhost \
   --db-name=magento \
   --db-user=root \
   --db-password=yourpassword \
   --admin-firstname=Admin \
   --admin-lastname=User \
   --admin-email=user@example.com \
   --admin-user=admin \
   --admin-password=admin123 \
   --language=en_US \
   --currency=USD \
   --timezone=America/Chicago \
   --use-rewrites=1
   ```

5. **Set Permissions**:
   ```sh
   sudo chown -R :www-data .
   sudo find . -type d -exec chmod 755 {} \;
   sudo find . -type f -exec chmod 644 {} \;
   ```

6. **Set Up Cron Jobs**:
   ```sh
   * * * * * /usr/bin/php /path_to_magento_root/bin/magento cron:run | grep -v "Ran jobs by schedule" >> /path_to_magento_root/var/log/magento.cron.log
   ```

7. **Deploy Static Content**:
   ```sh
   bin/magento setup:static-content:deploy -f
   ```

## Configuration

1. **Update Base URLs**:
   - Navigate to `Stores > Configuration > General > Web` in the Magento admin panel.
   - Update the `Base URL` and `Base URL (Secure)` fields.

2. **Flush Cache**:
   ```sh
   bin/magento cache:flush
   ```

## Usage

1. **Access the Admin Panel**:
   - Go to `http://yourdomain.com/admin`
   - Log in with the admin credentials provided during installation.

2. **Manage Products**:
   - Navigate to `Catalog > Products` to add or manage your products.

3. **Customize Themes**:
   - Edit or add new themes in the `app/design/frontend` directory.

4. **Install Extensions**:
   - Use Composer to install Magento extensions:
     ```sh
     composer require vendor/extension
     ```

## Contributing

We welcome contributions! Follow these steps to contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -am 'Add your feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Create a new Pull Request.

## Resources

### Useful Links
1. Intalling docker
https://docs.docker.com/desktop/install/windows-install/

2. Installing docker-compose 
https://docs.docker.com/compose/install/

3. Magento Installation requirements
https://experienceleague.adobe.com/en/docs/commerce-operations/installation-guide/system-requirements

4. Open Litespeed repository
https://github.com/litespeedtech/ols-docker-env/tree/v1.6.15

5. Installing chocolatey for windows
https://chocolatey.org/install


### Video Links
1. https://drive.google.com/file/d/10kXWJjwTfVKblpjAOK9c2vrHk35ffrMQ/view?usp=sharing
2. 


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

