# J.A.R.V.I.S. Android — projet natif V1

Cette version est un projet Android Studio natif en Kotlin (ce n'est pas une page web). Elle contient :
- interface Android futuriste et responsive ;
- conversation avec un fournisseur IA compatible OpenAI Chat Completions ;
- modes Général, Ingénierie, Programmation, Formation, Entreprise et Recherche ;
- dictée vocale via le service de reconnaissance Android ;
- lecture vocale des réponses via TextToSpeech ;
- réglages enregistrés localement sur le téléphone.

## Compiler l'APK
1. Installer Android Studio (version récente) et le SDK Android 35.
2. Ouvrir le dossier `JARVIS_ANDROID` dans Android Studio.
3. Attendre la synchronisation Gradle et accepter l'installation des composants SDK demandés.
4. Dans le menu **Build**, choisir **Build APK(s)**.
5. L'APK de débogage sera normalement dans `app/build/outputs/apk/debug/app-debug.apk`.

## Configuration
Dans l'application, toucher ⚙ et renseigner :
- URL de base du fournisseur, par exemple `https://api.openai.com/v1` ;
- nom exact du modèle disponible avec votre compte ;
- clé API valide.

La clé est stockée dans les préférences privées de l'application. Elle n'est pas chiffrée par ce prototype : ne partagez pas l'appareil déverrouillé ni ses sauvegardes. Les requêtes sont envoyées au fournisseur IA sélectionné et peuvent être payantes.

## Limites de cette V1
Ce projet source n'est pas un APK précompilé. Il n'a pas encore d'accès web intégré, d'actions système arbitraires, d'activation vocale permanente, de contrôle domotique, ni d'agents autonomes. L'assistant n'est pas omniscient ; vérifiez les résultats et faites valider les décisions critiques par des professionnels.

## Compilation dans le cloud depuis un téléphone (GitHub Actions)
Le dépôt inclut `.github/workflows/android-apk.yml`. Une fois les fichiers du projet placés dans un dépôt GitHub :
1. Ouvrez l'onglet **Actions** du dépôt et autorisez les workflows si demandé.
2. Choisissez **Build JARVIS Android APK**, puis **Run workflow** (ou poussez un commit sur `main`).
3. À la fin, ouvrez l'exécution terminée, puis téléchargez l'artifact **JARVIS-Android-debug-APK**.
4. Décompressez l'artifact téléchargé et installez `app-debug.apk` sur le téléphone. Android peut demander d'autoriser l'installation depuis cette source.

Cette compilation cloud nécessite un compte GitHub et une connexion internet. Le workflow compile le code source; il ne garantit pas que la clé API, le fournisseur IA ou toutes les fonctionnalités fonctionneront avant configuration et tests.
