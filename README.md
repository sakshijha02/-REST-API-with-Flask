# -REST-API-with-Flask
from flask import Flask, request, jsonify

app = Flask(__name__)

users = {}

@app.route('/')
def home():
    return "👋 Welcome to the User Management API!"

@app.route('/users', methods=['GET'])
def get_users():
    return jsonify(users), 200

@app.route('/users', methods=['POST'])
def add_user():
    data = request.get_json()
    username = data.get('username')
    email = data.get('email')

    
        

# PUT: Update existing user
@app.route('/users/<username>', methods=['PUT'])
def update_user(username):
    if username not in users:
        return jsonify({'error': 'User not found'}), 404

    
@app.route('/users/<username>', methods=['DELETE'])
def delete_user(username):
    if username not in users:
        return jsonify({'error': 'User not found'}), 404

if __name__ == '__main__':
    app.run(debug=True)
