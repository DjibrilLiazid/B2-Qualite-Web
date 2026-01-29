<template>
  <div class="min-h-screen bg-zinc-950 p-6">
    <div class="max-w-6xl mx-auto">
      <!-- Header -->
      <div class="text-center mb-8">
        <h1 class="text-4xl font-bold text-zinc-100 mb-2">
          Certificat de Sécurité HTTPS/SSL
        </h1>
        <p class="text-zinc-400">
          Protéger les données sensibles avec le chiffrement SSL/TLS
        </p>
      </div>

      <!-- Main Content -->
      <div class="space-y-8">
        <!-- HTTP vs HTTPS Comparison -->
        <div class="grid md:grid-cols-2 gap-6">
          <!-- HTTP (Insecure) -->
          <div
            class="bg-zinc-900 rounded-lg shadow-md p-6 border border-red-900"
          >
            <h2 class="text-xl font-bold text-red-400 mb-4 flex items-center">
              <span class="mr-2">❌</span> HTTP (Non Sécurisé)
            </h2>
            <div class="space-y-4">
              <div class="text-sm">
                <p class="text-zinc-400 mb-2">
                  <strong class="text-zinc-100">URL :</strong>
                </p>
                <div
                  class="bg-red-950 p-3 rounded border border-red-900 font-mono text-xs"
                >
                  http://example.com/login
                </div>
              </div>

              <div class="text-sm">
                <p class="text-zinc-400 mb-2">
                  <strong class="text-zinc-100">Caractéristiques :</strong>
                </p>
                <ul class="space-y-1 text-zinc-400">
                  <li>❌ Pas de cadenas</li>
                  <li>❌ Données non chiffrées</li>
                  <li>❌ Vulnérable aux interceptions</li>
                  <li>❌ Avertissement du navigateur</li>
                </ul>
              </div>

              <div class="text-sm">
                <p class="text-zinc-400 mb-2">
                  <strong class="text-zinc-100">Risques :</strong>
                </p>
                <ul class="space-y-1 text-red-300 text-xs">
                  <li>📡 Man-in-the-Middle attacks</li>
                  <li>🔓 Vol de données sensibles</li>
                  <li>⚠️ Modification en transit</li>
                  <li>🎭 Impersonation du serveur</li>
                </ul>
              </div>
            </div>
          </div>

          <!-- HTTPS (Secure) -->
          <div
            class="bg-zinc-900 rounded-lg shadow-md p-6 border border-green-900"
          >
            <h2 class="text-xl font-bold text-green-400 mb-4 flex items-center">
              <span class="mr-2">✓</span> HTTPS (Sécurisé)
            </h2>
            <div class="space-y-4">
              <div class="text-sm">
                <p class="text-zinc-400 mb-2">
                  <strong class="text-zinc-100">URL :</strong>
                </p>
                <div
                  class="bg-green-950 p-3 rounded border border-green-900 font-mono text-xs"
                >
                  🔒 https://example.com/login
                </div>
              </div>

              <div class="text-sm">
                <p class="text-zinc-400 mb-2">
                  <strong class="text-zinc-100">Caractéristiques :</strong>
                </p>
                <ul class="space-y-1 text-zinc-400">
                  <li>✓ Cadenas visible</li>
                  <li>✓ Données chiffrées (TLS)</li>
                  <li>✓ Certificat valide</li>
                  <li>✓ Authentification serveur</li>
                </ul>
              </div>

              <div class="text-sm">
                <p class="text-zinc-400 mb-2">
                  <strong class="text-zinc-100">Protections :</strong>
                </p>
                <ul class="space-y-1 text-green-300 text-xs">
                  <li>🔐 Chiffrement bout à bout</li>
                  <li>✓ Intégrité des données</li>
                  <li>🆔 Authentification du serveur</li>
                  <li>🔒 Prévention d'interception</li>
                </ul>
              </div>
            </div>
          </div>
        </div>

        <!-- SSL/TLS Certificate Info -->
        <div
          class="bg-zinc-900 rounded-lg shadow-md p-6 border border-zinc-800"
        >
          <h2 class="text-xl font-bold text-zinc-100 mb-4">
            Certificat SSL/TLS
          </h2>
          <p class="text-zinc-400 mb-6">
            Un certificat SSL (Secure Sockets Layer) / TLS (Transport Layer
            Security) est un document numérique qui authentifie l'identité d'un
            site et crée une connexion chiffrée.
          </p>

          <div class="grid md:grid-cols-2 gap-6">
            <!-- Certificate Info -->
            <div>
              <h3 class="text-sm font-bold text-zinc-100 mb-3">
                Informations du Certificat
              </h3>
              <div class="space-y-2 text-sm">
                <div class="bg-zinc-800 p-3 rounded border border-zinc-700">
                  <p class="text-zinc-400">
                    <strong class="text-zinc-100">Domaine :</strong>
                  </p>
                  <p class="text-zinc-300">example.com</p>
                </div>
                <div class="bg-zinc-800 p-3 rounded border border-zinc-700">
                  <p class="text-zinc-400">
                    <strong class="text-zinc-100">Émis par :</strong>
                  </p>
                  <p class="text-zinc-300">Let's Encrypt Authority</p>
                </div>
                <div class="bg-zinc-800 p-3 rounded border border-zinc-700">
                  <p class="text-zinc-400">
                    <strong class="text-zinc-100">Valide du :</strong>
                  </p>
                  <p class="text-zinc-300">01/01/2024 au 01/01/2025</p>
                </div>
                <div class="bg-zinc-800 p-3 rounded border border-zinc-700">
                  <p class="text-zinc-400">
                    <strong class="text-zinc-100">Algorithme :</strong>
                  </p>
                  <p class="text-zinc-300">RSA 2048 bits ou ECDSA 256 bits</p>
                </div>
              </div>
            </div>

            <!-- Certificate Chain -->
            <div>
              <h3 class="text-sm font-bold text-zinc-100 mb-3">
                Chaîne d'Autorité
              </h3>
              <div class="space-y-2">
                <div class="bg-green-950 p-3 rounded border border-green-900">
                  <p class="text-xs text-green-400 font-mono mb-1">
                    🔒 Certificat du serveur
                  </p>
                  <p class="text-xs text-green-300">example.com</p>
                </div>
                <div class="text-center text-zinc-500">↓</div>
                <div class="bg-blue-950 p-3 rounded border border-blue-900">
                  <p class="text-xs text-blue-400 font-mono mb-1">
                    📄 Certificat intermédiaire
                  </p>
                  <p class="text-xs text-blue-300">Let's Encrypt Authority</p>
                </div>
                <div class="text-center text-zinc-500">↓</div>
                <div class="bg-purple-950 p-3 rounded border border-purple-900">
                  <p class="text-xs text-purple-400 font-mono mb-1">
                    🏛️ Certificat racine
                  </p>
                  <p class="text-xs text-purple-300">Root Authority</p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Security Indicators -->
        <div
          class="bg-zinc-900 rounded-lg shadow-md p-6 border border-zinc-800"
        >
          <h2 class="text-xl font-bold text-zinc-100 mb-4">
            Indicateurs de Sécurité du Navigateur
          </h2>
          <p class="text-zinc-400 mb-6">
            Les navigateurs modernes affichent des indicateurs visuels pour
            confirmer qu'une page est sécurisée.
          </p>

          <div class="space-y-4">
            <div
              v-for="indicator in securityIndicators"
              :key="indicator.id"
              class="bg-zinc-800 p-4 rounded border border-zinc-700"
            >
              <h3 class="text-sm font-bold text-zinc-100 mb-2">
                {{ indicator.name }}
              </h3>
              <p class="text-sm text-zinc-400 mb-3">
                {{ indicator.description }}
              </p>
              <div
                class="bg-zinc-900 p-3 rounded text-xs font-mono border border-zinc-700"
              >
                <span class="text-green-400">✓</span>
                <span class="text-zinc-300">{{ indicator.example }}</span>
              </div>
            </div>
          </div>
        </div>

        <!-- OpenID Authentication -->
        <div
          class="bg-zinc-900 rounded-lg shadow-md p-6 border border-zinc-800"
        >
          <h2 class="text-xl font-bold text-zinc-100 mb-4">
            Authentification Décentralisée (OpenID)
          </h2>
          <p class="text-zinc-400 mb-6">
            OpenID permet aux utilisateurs de se connecter avec un fournisseur
            d'identité externe et centralisé.
          </p>

          <div class="grid md:grid-cols-2 gap-6">
            <div>
              <h3 class="text-sm font-bold text-zinc-100 mb-3">Avantages</h3>
              <ul class="space-y-2">
                <li class="flex items-start">
                  <span class="text-green-400 mr-2">✓</span>
                  <span class="text-zinc-300 text-sm">
                    Un seul compte pour plusieurs services
                  </span>
                </li>
                <li class="flex items-start">
                  <span class="text-green-400 mr-2">✓</span>
                  <span class="text-zinc-300 text-sm">
                    Pas de partage de mot de passe
                  </span>
                </li>
                <li class="flex items-start">
                  <span class="text-green-400 mr-2">✓</span>
                  <span class="text-zinc-300 text-sm">
                    Fournisseur certifié gère la sécurité
                  </span>
                </li>
                <li class="flex items-start">
                  <span class="text-green-400 mr-2">✓</span>
                  <span class="text-zinc-300 text-sm">
                    Meilleure gestion de l'identité
                  </span>
                </li>
              </ul>
            </div>

            <div>
              <h3 class="text-sm font-bold text-zinc-100 mb-3">
                Flux de Connexion OpenID
              </h3>
              <div class="space-y-2 text-sm">
                <div class="bg-zinc-800 p-2 rounded border border-zinc-700">
                  <p class="text-zinc-300">
                    1. Utilisateur clique "Se connecter avec OpenID"
                  </p>
                </div>
                <div class="text-center text-zinc-500 text-xs">↓</div>
                <div class="bg-zinc-800 p-2 rounded border border-zinc-700">
                  <p class="text-zinc-300">
                    2. Redirection vers fournisseur OpenID
                  </p>
                </div>
                <div class="text-center text-zinc-500 text-xs">↓</div>
                <div class="bg-zinc-800 p-2 rounded border border-zinc-700">
                  <p class="text-zinc-300">3. Authentification sécurisée</p>
                </div>
                <div class="text-center text-zinc-500 text-xs">↓</div>
                <div class="bg-green-950 p-2 rounded border border-green-900">
                  <p class="text-green-300">4. Retour au site avec token</p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Common Certificate Errors -->
        <div class="bg-zinc-900 rounded-lg shadow-md p-6 border border-red-900">
          <h2 class="text-xl font-bold text-red-400 mb-4">
            Erreurs Courantes de Certificat
          </h2>
          <div class="space-y-3">
            <div
              v-for="error in certificateErrors"
              :key="error.id"
              class="bg-red-950 p-4 rounded border border-red-900"
            >
              <h3 class="text-sm font-bold text-red-300 mb-1">
                {{ error.name }}
              </h3>
              <p class="text-xs text-red-200 mb-2">{{ error.description }}</p>
              <p class="text-xs text-red-400">
                <strong>Solution :</strong> {{ error.solution }}
              </p>
            </div>
          </div>
        </div>

        <!-- Best Practices -->
        <div
          class="bg-zinc-900 rounded-lg shadow-md p-6 border border-zinc-800"
        >
          <h2 class="text-xl font-bold text-zinc-100 mb-4">Bonnes Pratiques</h2>
          <ul class="space-y-3">
            <li class="flex items-start">
              <span class="text-green-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Utiliser <strong class="text-zinc-100">HTTPS partout</strong>,
                pas seulement sur les pages sensibles
              </span>
            </li>
            <li class="flex items-start">
              <span class="text-green-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Rediriger automatiquement
                <strong class="text-zinc-100">HTTP vers HTTPS</strong>
              </span>
            </li>
            <li class="flex items-start">
              <span class="text-green-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Configurer
                <strong class="text-zinc-100"
                  >HSTS (HTTP Strict Transport Security)</strong
                >
                pour forcer HTTPS
              </span>
            </li>
            <li class="flex items-start">
              <span class="text-green-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Renouveler le certificat
                <strong class="text-zinc-100">avant expiration</strong>
              </span>
            </li>
            <li class="flex items-start">
              <span class="text-green-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Utiliser des certificats
                <strong class="text-zinc-100">RSA 2048+ ou ECDSA 256+</strong>
              </span>
            </li>
            <li class="flex items-start">
              <span class="text-green-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Mettre en place les
                <strong class="text-zinc-100">en-têtes de sécurité</strong>
                (CSP, X-Frame-Options, etc.)
              </span>
            </li>
            <li class="flex items-start">
              <span class="text-green-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Considérer <strong class="text-zinc-100">OpenID</strong> pour
                l'authentification centralisée
              </span>
            </li>
          </ul>
        </div>

        <!-- Implementation Checklist -->
        <div
          class="bg-zinc-900 rounded-lg shadow-md p-6 border border-zinc-800"
        >
          <h2 class="text-xl font-bold text-zinc-100 mb-4">
            Checklist d'Implémentation
          </h2>
          <div class="space-y-3">
            <label
              v-for="(item, index) in checklist"
              :key="index"
              class="flex items-center p-3 rounded bg-zinc-800 cursor-pointer hover:bg-zinc-700 transition"
            >
              <input
                type="checkbox"
                v-model="checklist[index].checked"
                class="w-4 h-4 rounded border-zinc-600"
              />
              <span class="ml-3 text-zinc-300">{{ item.text }}</span>
            </label>
          </div>
        </div>

        <!-- Testing Procedures -->
        <div
          class="bg-zinc-900 rounded-lg shadow-md p-6 border border-zinc-800"
        >
          <h2 class="text-xl font-bold text-zinc-100 mb-4">
            Procédures de Vérification
          </h2>
          <div class="space-y-4">
            <div class="bg-zinc-800 p-4 rounded border border-zinc-700">
              <h3 class="text-sm font-bold text-zinc-100 mb-2">
                1. Tester la Redirection HTTP → HTTPS
              </h3>
              <p class="text-sm text-zinc-400">
                Visitez le site via http (sans https) et vérifiez que vous êtes
                automatiquement redirigé vers la version HTTPS.
              </p>
            </div>

            <div class="bg-zinc-800 p-4 rounded border border-zinc-700">
              <h3 class="text-sm font-bold text-zinc-100 mb-2">
                2. Vérifier les Pages Sensibles
              </h3>
              <p class="text-sm text-zinc-400">
                Vérifier que les pages contenant des données sensibles (login,
                paiement, données bancaires) sont en HTTPS.
              </p>
            </div>

            <div class="bg-zinc-800 p-4 rounded border border-zinc-700">
              <h3 class="text-sm font-bold text-zinc-100 mb-2">
                3. Inspecter le Certificat
              </h3>
              <p class="text-sm text-zinc-400">
                Cliquez sur le cadenas dans la barre de navigation pour vérifier
                les détails du certificat SSL/TLS.
              </p>
            </div>

            <div class="bg-zinc-800 p-4 rounded border border-zinc-700">
              <h3 class="text-sm font-bold text-zinc-100 mb-2">
                4. Vérifier le Code du Formulaire
              </h3>
              <p class="text-sm text-zinc-400">
                Si des données sensibles sont saisies sur une page HTTP,
                vérifier que l'attribut "action" du formulaire pointe vers HTTPS
                (moins sécurisé mais acceptable pour données non-bancaires).
              </p>
            </div>

            <div class="bg-zinc-800 p-4 rounded border border-zinc-700">
              <h3 class="text-sm font-bold text-zinc-100 mb-2">
                5. Utiliser des Outils de Vérification
              </h3>
              <p class="text-sm text-zinc-400">
                Utiliser des services comme SSL Labs ou Qualsys pour un audit
                complet du certificat.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const securityIndicators = [
  {
    id: 1,
    name: "Cadenas dans la Barre d'Adresse",
    description:
      "Un cadenas vert apparaît à côté de l'URL, indiquant une connexion sécurisée.",
    example: '🔒 https://example.com',
  },
  {
    id: 2,
    name: 'URL en HTTPS',
    description: "L'adresse commence par 'https://' au lieu de 'http://'.",
    example: '🔐 https://secure.example.com/account',
  },
  {
    id: 3,
    name: 'Détails du Certificat',
    description:
      'Cliquer sur le cadenas affiche les informations du certificat SSL/TLS.',
    example: '📄 Certificat valide pour example.com',
  },
  {
    id: 4,
    name: "Barre d'Adresse Colorée",
    description:
      "Certains navigateurs changent la couleur de la barre d'adresse pour HTTPS.",
    example: '🟢 Barre verte pour https://',
  },
  {
    id: 5,
    name: 'EV Certificate (Optional)',
    description:
      "Un certificat EV affiche le nom de l'organisation dans la barre d'adresse.",
    example: '🏢 Nom Entreprise | https://example.com',
  },
]

const certificateErrors = [
  {
    id: 1,
    name: 'Certificat Expiré',
    description: "Le certificat SSL a dépassé sa date d'expiration.",
    solution: "Renouveler le certificat auprès de l'autorité de certification.",
  },
  {
    id: 2,
    name: 'Nom de Domaine Non Valide',
    description: 'Le certificat est valide mais pour un domaine différent.',
    solution:
      'Obtenir un certificat pour le bon domaine ou utiliser un certificat wildcard.',
  },
  {
    id: 3,
    name: 'Autorité de Certification Non Reconnue',
    description:
      "L'autorité qui a émis le certificat n'est pas reconnue par le navigateur.",
    solution:
      "Utiliser une autorité de certification reconnue (Let's Encrypt, DigiCert, etc.).",
  },
  {
    id: 4,
    name: 'Certificat Auto-Signé',
    description: "Le certificat n'est pas signé par une autorité reconnue.",
    solution:
      'Obtenir un certificat signé par une autorité de certification de confiance.',
  },
  {
    id: 5,
    name: 'Chaîne de Certificats Incomplète',
    description: 'Un ou plusieurs certificats intermédiaires manquent.',
    solution:
      'Configurer le serveur pour inclure tous les certificats de la chaîne.',
  },
]

const checklist = ref([
  {
    text: 'Obtenir un certificat SSL/TLS valide',
    checked: false,
  },
  {
    text: 'Configurer le serveur pour HTTPS',
    checked: false,
  },
  {
    text: 'Rediriger HTTP vers HTTPS',
    checked: false,
  },
  {
    text: "Configurer l'en-tête HSTS",
    checked: false,
  },
  {
    text: 'Utiliser RSA 2048+ ou ECDSA 256+',
    checked: false,
  },
  {
    text: 'Mettre en place les en-têtes de sécurité (CSP, X-Frame-Options)',
    checked: false,
  },
  {
    text: 'Vérifier les pages sensibles en HTTPS',
    checked: false,
  },
  {
    text: 'Tester la redirection HTTP → HTTPS',
    checked: false,
  },
  {
    text: 'Vérifier la validité du certificat',
    checked: false,
  },
  {
    text: 'Mettre en place le renouvellement automatique',
    checked: false,
  },
  {
    text: "Considérer OpenID pour l'authentification",
    checked: false,
  },
])
</script>
