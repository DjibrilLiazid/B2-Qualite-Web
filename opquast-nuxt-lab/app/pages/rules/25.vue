<template>
  <div class="min-h-screen bg-zinc-950 p-6">
    <div class="max-w-6xl mx-auto">
      <!-- Header -->
      <div class="text-center mb-8">
        <h1 class="text-4xl font-bold text-zinc-100 mb-2">
          Configuration Referrer-Policy
        </h1>
        <p class="text-zinc-400">
          Protégez la vie privée des utilisateurs en contrôlant les informations
          de navigation
        </p>
      </div>

      <!-- Main Content -->
      <div class="space-y-8">
        <!-- What is Referrer-Policy -->
        <div
          class="bg-zinc-900 rounded-lg shadow-md p-6 border border-zinc-800"
        >
          <h2 class="text-xl font-bold text-zinc-100 mb-3">
            Qu'est-ce que le Referrer-Policy ?
          </h2>
          <p class="text-zinc-400 mb-4">
            L'en-tête HTTP
            <code class="bg-zinc-800 px-2 py-1 rounded text-zinc-200"
              >Referrer-Policy</code
            >
            contrôle le niveau d'information transmis au serveur de destination
            lorsqu'un utilisateur clique sur un lien ou accède à une ressource.
            Il protège la vie privée en limitant l'exposition des URLs visitées.
          </p>
          <div class="bg-zinc-800 p-4 rounded border border-zinc-700">
            <p class="text-sm text-zinc-300">
              <strong class="text-zinc-100">Exemple :</strong> Si votre page
              contient un lien vers un site externe, sans Referrer-Policy, ce
              site peut voir l'URL complète de la page d'où vient l'utilisateur.
            </p>
          </div>
        </div>

        <!-- Policy Options -->
        <div
          class="bg-zinc-900 rounded-lg shadow-md p-6 border border-zinc-800"
        >
          <h2 class="text-xl font-bold text-zinc-100 mb-4">
            Options de Politique Referrer
          </h2>
          <p class="text-zinc-400 mb-6">
            Sélectionnez une politique pour voir comment elle fonctionne :
          </p>

          <div class="space-y-4">
            <div
              v-for="policy in policies"
              :key="policy.id"
              @click="selectPolicy(policy.id)"
              class="p-4 rounded border-2 transition cursor-pointer"
              :class="[
                selectedPolicy === policy.id
                  ? 'bg-zinc-800 border-zinc-500'
                  : 'bg-zinc-950 border-zinc-700 hover:border-zinc-600',
              ]"
            >
              <div class="flex items-start">
                <div class="flex-1">
                  <h3 class="font-bold text-zinc-100 mb-1">
                    {{ policy.name }}
                  </h3>
                  <p class="text-sm text-zinc-400 mb-2">
                    {{ policy.description }}
                  </p>
                  <div class="text-xs text-zinc-500">
                    <p class="mb-1">
                      <strong>Niveau de sécurité :</strong>
                      {{ policy.security }}
                    </p>
                    <p><strong>Use case :</strong> {{ policy.useCase }}</p>
                  </div>
                </div>
                <div class="ml-4">
                  <span
                    v-if="selectedPolicy === policy.id"
                    class="inline-block w-6 h-6 rounded-full bg-zinc-500 flex items-center justify-center"
                  >
                    <svg
                      class="w-4 h-4 text-zinc-950"
                      fill="currentColor"
                      viewBox="0 0 20 20"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M16.707 5.293a1 1 0 010 1.414l-8 8a1 1 0 01-1.414 0l-4-4a1 1 0 011.414-1.414L8 12.586l7.293-7.293a1 1 0 011.414 0z"
                        clip-rule="evenodd"
                      />
                    </svg>
                  </span>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Details of Selected Policy -->
        <div
          class="bg-zinc-900 rounded-lg shadow-md p-6 border border-zinc-800"
        >
          <h2 class="text-xl font-bold text-zinc-100 mb-4">
            Détails : {{ selectedPolicyData.name }}
          </h2>

          <!-- HTTP Header Example -->
          <div class="mb-6">
            <h3 class="text-sm font-bold text-zinc-100 mb-2">En-tête HTTP</h3>
            <div
              class="bg-zinc-800 p-3 rounded border border-zinc-700 font-mono text-sm"
            >
              <span class="text-zinc-400">HTTP/1.1 200 OK</span><br />
              <span class="text-green-400">
                Referrer-Policy: {{ selectedPolicyData.headerValue }}
              </span>
            </div>
          </div>

          <!-- Configuration Example -->
          <div class="mb-6">
            <h3 class="text-sm font-bold text-zinc-100 mb-2">
              Configuration Serveur (Nginx)
            </h3>
            <div
              class="bg-zinc-800 p-3 rounded border border-zinc-700 font-mono text-sm"
            >
              <span class="text-zinc-400">add_header Referrer-Policy</span>
              <span class="text-blue-400"
                >"{{ selectedPolicyData.headerValue }}"</span
              >
              <span class="text-zinc-400">always;</span>
            </div>
          </div>

          <!-- Scenario -->
          <div class="mb-6">
            <h3 class="text-sm font-bold text-zinc-100 mb-2">
              Exemple de Comportement
            </h3>
            <div
              class="bg-zinc-800 p-4 rounded border border-zinc-700 text-sm space-y-2"
            >
              <div>
                <span class="text-zinc-400">
                  <strong>Page actuelle :</strong>
                  https://example.com/articles/secret.html
                </span>
              </div>
              <div>
                <span class="text-zinc-400">
                  <strong>Lien vers :</strong> https://external.com/resource
                </span>
              </div>
              <div>
                <span class="text-zinc-400">
                  <strong>Referrer envoyé :</strong>
                </span>
                <br />
                <span class="text-green-400">{{
                  selectedPolicyData.behavior
                }}</span>
              </div>
            </div>
          </div>

          <!-- Advantages -->
          <div>
            <h3 class="text-sm font-bold text-zinc-100 mb-3">Avantages</h3>
            <ul class="space-y-2">
              <li
                v-for="(advantage, index) in selectedPolicyData.advantages"
                :key="index"
                class="flex items-start"
              >
                <svg
                  class="w-5 h-5 text-green-500 mr-3 mt-0.5 flex-shrink-0"
                  fill="currentColor"
                  viewBox="0 0 20 20"
                >
                  <path
                    fill-rule="evenodd"
                    d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                    clip-rule="evenodd"
                  />
                </svg>
                <span class="text-zinc-300">{{ advantage }}</span>
              </li>
            </ul>
          </div>
        </div>

        <!-- Best Practices -->
        <div
          class="bg-zinc-900 rounded-lg shadow-md p-6 border border-zinc-800"
        >
          <h2 class="text-xl font-bold text-zinc-100 mb-4">Bonnes Pratiques</h2>
          <ul class="space-y-3">
            <li class="flex items-start">
              <span class="text-zinc-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Utiliser <strong class="text-zinc-100">no-referrer</strong> pour
                la sécurité maximale, sauf si le tracking est nécessaire
              </span>
            </li>
            <li class="flex items-start">
              <span class="text-zinc-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Appliquer la politique à
                <strong class="text-zinc-100">toutes les pages</strong> du site
              </span>
            </li>
            <li class="flex items-start">
              <span class="text-zinc-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Vérifier la présence de l'en-tête avec les outils de
                développement (F12 → Network → Headers)
              </span>
            </li>
            <li class="flex items-start">
              <span class="text-zinc-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Combiner avec d'autres en-têtes de sécurité (CSP,
                X-Frame-Options, etc.)
              </span>
            </li>
            <li class="flex items-start">
              <span class="text-zinc-400 mr-3">✓</span>
              <span class="text-zinc-300">
                Documenter le choix de politique et les raisons dans la
                politique de confidentialité
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
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const selectedPolicy = ref('no-referrer')

const policies = [
  {
    id: 'no-referrer',
    name: 'no-referrer',
    description:
      "L'en-tête Referer ne sera jamais envoyé. Offre la protection maximale.",
    security: '🔒 Maximale',
    useCase: 'Sites sensibles, données confidentielles',
    headerValue: 'no-referrer',
    behavior: 'Aucune information (pas de referrer)',
    advantages: [
      'Sécurité et confidentialité maximales',
      "Aucune information de navigation n'est divulguée",
      'Idéal pour les sites bancaires et médicaux',
      'Préserve la vie privée des utilisateurs',
    ],
  },
  {
    id: 'same-origin',
    name: 'same-origin',
    description:
      "L'en-tête Referer est envoyé uniquement pour les requêtes vers le même domaine.",
    security: '🔒 Bonne',
    useCase: 'Sites standards sans ressources externes sensibles',
    headerValue: 'same-origin',
    behavior:
      'https://example.com/articles/secret.html (pour même-origine)\nAucun referrer (pour cross-origin)',
    advantages: [
      'Bonne balance sécurité/fonctionnalité',
      'Partage de données seulement en interne',
      'Bloque les informations vers les domaines externes',
      'Recommandé par défaut',
    ],
  },
  {
    id: 'strict-origin',
    name: 'strict-origin',
    description:
      "Envoie uniquement l'origine (sans le chemin) pour les requêtes de même sécurité.",
    security: '🔒 Bonne',
    useCase: "Sites nécessitant du suivi d'origine",
    headerValue: 'strict-origin',
    behavior:
      'https://example.com/ (origine uniquement, sans chemin)\nAucun referrer (HTTP vers HTTPS)',
    advantages: [
      "Divulgue uniquement l'origine, jamais le chemin complet",
      'Améliore le respect de la vie privée',
      "Utile pour l'analyse sans révéler les URLs sensibles",
      'Ne descend pas au HTTP',
    ],
  },
  {
    id: 'strict-origin-when-cross-origin',
    name: 'strict-origin-when-cross-origin',
    description:
      "Envoie l'URL complète en same-origin, seulement l'origine en cross-origin.",
    security: '🔒 Modérée',
    useCase: 'Sites nécessitant du suivi interne et externe limité',
    headerValue: 'strict-origin-when-cross-origin',
    behavior:
      'https://example.com/articles/secret.html (même-origine)\nhttps://example.com/ (cross-origin, origine uniquement)',
    advantages: [
      'Équilibre entre fonctionnalité et sécurité',
      'Partage complet en interne, minimal en externe',
      "Utile pour les systèmes d'analytics",
      'Comportement par défaut dans les navigateurs modernes',
    ],
  },
]

const selectedPolicyData = computed(() => {
  return policies.find((p) => p.id === selectedPolicy.value) || policies[0]
})

const selectPolicy = (policyId) => {
  selectedPolicy.value = policyId
}

const checklist = ref([
  {
    text: "Configurer l'en-tête Referrer-Policy sur le serveur",
    checked: false,
  },
  {
    text: 'Choisir la politique appropriée (recommandé : no-referrer ou same-origin)',
    checked: false,
  },
  {
    text: 'Appliquer à toutes les pages du site',
    checked: false,
  },
  {
    text: "Vérifier l'en-tête HTTP avec les outils de développement",
    checked: false,
  },
  {
    text: 'Tester depuis plusieurs navigateurs',
    checked: false,
  },
  {
    text: 'Documenter dans la politique de confidentialité',
    checked: false,
  },
  {
    text: "Mettre en place un monitoring pour vérifier la présence de l'en-tête",
    checked: false,
  },
])
</script>
