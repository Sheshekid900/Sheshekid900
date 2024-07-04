<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>News Website</title>
    <link rel="stylesheet" href="styles.css">
    <script src="https://www.gstatic.com/firebasejs/9.0.0/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.0.0/firebase-auth.js"></script>
    <script>
        // Firebase configuration
        const firebaseConfig = {
            apiKey: "YOUR_API_KEY",
            authDomain: "YOUR_AUTH_DOMAIN",
            projectId: "YOUR_PROJECT_ID",
            storageBucket: "YOUR_STORAGE_BUCKET",
            messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
            appId: "YOUR_APP_ID"
        };
        
        // Initialize Firebase
        firebase.initializeApp(firebaseConfig);

        // Firebase Authentication
        const auth = firebase.auth();

        // Sign in with Google
        function signInWithGoogle() {
            const provider = new firebase.auth.GoogleAuthProvider();
            auth.signInWithPopup(provider).then(result => {
                console.log(result.user);
            }).catch(error => {
                console.log(error);
            });
        }

        // Sign in with Apple
        function signInWithApple() {
            const provider = new firebase.auth.OAuthProvider('apple.com');
            auth.signInWithPopup(provider).then(result => {
                console.log(result.user);
            }).catch(error => {
                console.log(error);
            });
        }

        // Sign in with Microsoft
        function signInWithMicrosoft() {
            const provider = new firebase.auth.OAuthProvider('microsoft.com');
            auth.signInWithPopup(provider).then(result => {
                console.log(result.user);
            }).catch(error => {
                console.log(error);
            });
        }
    </script>
</head>
<body>
    <header>
        <h1>Welcome to the News Website</h1>
        <button onclick="signInWithGoogle()">Sign in with Google</button>
        <button onclick="signInWithApple()">Sign in with Apple</button>
        <button onclick="signInWithMicrosoft()">Sign in with Microsoft</button>
    </header>
    <main>
        <h2>Latest News</h2>
        <div id="news-container">
            <!-- News articles will be displayed here -->
        </div>
    </main>
</body>
</html>-
