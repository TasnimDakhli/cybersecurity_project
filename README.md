

# Cybersecurity Project
#### Please note: For better viewing experience, and more details , consider viewing the PDF version of this report, "CyberSecurity.pdf", available in this repository.
## Overview
This project covers the implementation and configuration of various network security protocols and services using OpenLDAP, SSH, Apache, OpenVPN, and Kerberos. The goal is to enhance authentication, secure communication, and manage network services efficiently.

## Table of Contents:
1. [OpenLDAP Configuration](#openldap-configuration)
2. [SSH Authentication](#ssh-authentication)
3. [Apache Integration](#apache-integration)
4. [OpenVPN Setup](#openvpn-setup)
5. [DNS Network Services](#dns-network-services)
6. [Kerberos Authentication](#kerberos-authentication)
7. [Validation and Testing](#validation-and-testing)

---

## OpenLDAP Configuration

OpenLDAP is used for centralized authentication and managing user data. This section covers the server-side and client-side configuration, group and user creation, adding x509 certificates, and securing the LDAP communication using LDAPS.

### Steps:
1. **Server-Side Setup:**
   - Set the full hostname.
   - Install LAM (LDAP Account Manager).
   - Configure Apache for PHP FastCGI and restart the server.
   - Create groups and users.
   
2. **Client-Side Setup:**
   - Ensure OpenLDAP service is running.
   - Update the system and install required packages.
   - Modify configuration files and restart services.
   - Verify user authentication.

3. **Security:**
   - Generate self-signed certificates and configure LDAP to use SSL/TLS (LDAPS) for secure communication.

## SSH Authentication

SSH is configured to authenticate using OpenLDAP. This ensures secure remote server management.

### Steps:
- Modify the `/etc/nsswitch.conf` and PAM files for OpenLDAP integration.
- Restrict SSH access to specific groups (e.g., `it-grp`).
- Test SSH access with both authorized and unauthorized users.

## Apache Integration

Apache is configured to use OpenLDAP for authentication, allowing only members of specific groups to access the server.

### Steps:
- Install Apache and enable the required modules.
- Modify Apache configuration to restrict access to certain groups.
- Test the access for authorized and unauthorized users.

## OpenVPN Setup

OpenVPN is configured to use OpenLDAP for authentication, providing secure VPN access.

### Steps:
- Install OpenVPN on both server and client sides.
- Configure the VPN server and integrate LDAP for user authentication.
- Test the connection with different users.

## DNS Network Services

DNS is configured to manage domain names for the OpenLDAP, Apache, and OpenVPN services.

### Steps:
- Add IP addresses and FQDNs to the `/etc/hosts` file.
- Install and configure `bind9` for DNS services.
- Create necessary DNS records for OpenLDAP, Apache, and OpenVPN.

## Kerberos Authentication

Kerberos is used for secure, centralized authentication with SSH.

### Steps:
1. Set up DNS and modify hostnames.
2. Install Kerberos packages and configure realms.
3. Create principals for users and hosts.
4. Enable password policies for Kerberos principals.
5. Integrate Kerberos with SSH for secure login without passwords.

## Validation and Testing

Each service and protocol was tested to ensure proper integration and security. Testing involved validating access control, authentication, and the secure transmission of data.

---

By following this guide, you will be able to replicate the setup used in this cybersecurity project to implement a secure and efficient network environment.

