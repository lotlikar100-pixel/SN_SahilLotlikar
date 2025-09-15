# SN_SahilLotlikar
technical round

# Personal Home Cloud with Secure Multi-Level Access
A Personal Home Cloud with Secure Multi-Level Access is a self-hosted cloud storage system designed for home use, which enables secure, remote access to personal and family data. It implements role-based access control, allowing different users—such as family members and guests—to access only the data and resources relevant to their roles. The system uses encryption, network security measures, and monitoring tools to protect data and ensure privacy.

# Home cloud server and segmentation
def authenticate(username, password):
    user = db.get_user(username)
    if user and verify_password(password, user.password_hash):
        return user.role
    else:
        return "Access Denied"

# Role based access control
def has_access(user, folder):
    if folder in user.allowed_folders:
        return True
    else:
        return False

 # Guest access portal
 def generate_guest_token(user, expiry_time):
    token = create_random_token()
    db.save_token(token, user, expiry_time)
    return token

   # For remote accessibility we can use VPN + https         

# Block diagram
                    +-----------------------------+
                |      Remote User Devices     |
                +-----------------------------+
                           |
                           v
                +-----------------------------+
                |      VPN Gateway/Firewall    |
                +-----------------------------+
                           |
                           v
                +-----------------------------+
                |      HTTPS Reverse Proxy     |
                +-----------------------------+
                           |
                           v
                +-----------------------------+
                |      Home Cloud Server       |
                |  (Web App + API + Storage)  |
                +-----------------------------+
                           |
        +------------------+------------------+
        |                  |                  |
        v                  v                  v
+---------------+  +---------------+  +---------------+
|   Self Vault  |  | Family Vault  |  | Guest Vault   |
+---------------+  +---------------+  +---------------+
        |                  |                  |
        v                  v                  v
+-----------------------------------------------------+
|           Encrypted Storage Backend                 |
+-----------------------------------------------------+
# ROADMAP
1. Repository Initialization: Create a GitHub repository. 
2. Home Cloud Server & Segmentation: Set up storage server and  Implement user-based folder segmentation.
3. Role-Based Access Control: Design user roles and permissions.
4. Guest Access Portal: Build guest portal for restricted, time-bound access.
5. Network Security Controls:  Configure firewall, VPN, and device authentication.
