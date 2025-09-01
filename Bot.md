# Bienvenue sur le bot du groupe LAMOTTE !

1. Ce chatbot a été développé par **Adrien ROUX**, alternant en licence professionnelle, dans le cadre d’un projet de test.  
2. Il n’est pas destiné à un usage quotidien au sein de l’entreprise.  
3. Son utilisation est autorisée uniquement pour la phase d’expérimentation.  
👉 Merci de vos retours.

---

##  Q/R — Conflits bailleurs / locataires

<details>
  <summary><strong>Délai de restitution du dépôt de garantie</strong></summary>
- Bail vide (logement en bon état) : **1 mois** après remise des clés.  
- Avec retenues justifiées (dégradations) : **2 mois** max.  
- Source : Code civil art. 22 loi 6 juillet 1989.  
- ⚠️ En cas de litige → proposer état des lieux contradictoire.
</details>

<details>
  <summary><strong>Qui paie les réparations ? (exemples)</strong></summary>
- **Locataire** : petites réparations (ampoules, joints, ménage).  
- **Bailleur** : grosses réparations (toiture, chaudière…).  
- Cas limites (ex : infiltration) = source fréquente de conflit.  
- Réf. : décret n°87-712 du 26 août 1987.
</details>

<details>
  <summary><strong>Que faire si le locataire refuse l’état des lieux de sortie ?</strong></summary>
- Réaliser l’état des lieux par huissier si absence/refus.  
- Frais partagés.  
- Prévoir notification écrite (mail ou recommandé), garder preuve.
</details>

<!-- Ajoute d'autres <details> ici selon besoin... -->

---

##  Ou saisissez votre question ci-dessous :

<div id="chat-interface" style="margin-top: 1em;">
  <input type="text" id="user-input" placeholder="Posez votre question..." style="width: 80%;" />
  <button id="btn-send">Envoyer</button>
  <p id="bot-response" style="margin-top: 1em; color: #444;"></p>
</div>

<script>
  (function() {
    const faq = [
      {
        keywords: ["dépôt", "délai", "garantie", "restitution"],
        answer: "Délai de restitution du dépôt de garantie : 1 mois si logement rendu en bon état, jusqu’à 2 mois si retenues justifiées."
      },
      {
        keywords: ["réparations", "qui", "paie"],
        answer: "Réparations : le locataire prend en charge l’entretien courant, le bailleur les grosses réparations (ex : chaudière, toiture)."
      },
      {
        keywords: ["état des lieux", "refuse", "sortie"],
        answer: "Si le locataire refuse l’état des lieux de sortie : faire intervenir un huissier. Frais partagés, notifier par écrit et garder preuve."
      }
      // Ajoute d'autres objets FAQ ici...
    ];

    const input = document.getElementById("user-input");
    const btn = document.getElementById("btn-send");
    const response = document.getElementById("bot-response");

    btn.addEventListener("click", () => {
      const text = input.value.trim().toLowerCase();
      if (!text) {
        response.textContent = "Veuillez écrire une question.";
        return;
      }
      const found = faq.find(item =>
        item.keywords.every(kw => text.includes(kw))
      );
      response.textContent = found ? found.answer : "Désolé, je ne comprends pas votre requête.";
    });
  })();
</script>
