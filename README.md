# CS 310: Final Project

## Summary
- This project uses Ansible to write a declarative configuration for the made-up company "CraftRoast". We hook up their Bagisto e-commerce site using Docker. We also install a grafana instance for monitoring their e-commerce site. The server has an admin account and two developer accounts.

## Usage
- How to run the project
  - Clone the repo.
  - Run these commands:
    - Install pipx
      - python3 -m pip install --user pipx
      - python3 -m pipx ensurepath
    - Install Ansible via pix
      - pipx install --include-deps ansible
    - Install Ansible Galaxy Collections
      - ansible-galaxy collection install community.docker
    - Follow the Docker installation guide for Bagisto using the first link in 'Resources'
      - docker pull webkul/bagisto:2.3.6
      - docker run -it -d -p 80:80 webkul/bagisto:2.3.6
        - ^ NOTE ^ port 80 may be in use. If so, use a differenct port number
  - Change inventory.ini to be your IP address
  - Run the main playbook:
    - ansible-playbook -i inventory.ini playbooks/smoke.yml --ask-become-pass
    - (You will have to enter your sudo password)

## Resources
- Document used
  - https://devdocs.bagisto.com/getting-started/installation.html#%F0%9F%90%B3-docker-installation
  - https://docs.ansible.com/projects/ansible/latest/collections/community/docker/index.html#plugins-in-community-docker
  - https://docs.ansible.com/projects/ansible/latest/collections/ansible/builtin/index.html#plugins-in-ansible-builtin

- How to find the documentation for this project.
  - Go to the doc folder for each of the playbooks.
