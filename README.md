- L’action qui ouvre la réservation doit utiliser un élément HTML natif :
Remplacé par `<button type="button" className="booking-trigger">`


- La fenêtre doit avoir un rôle et un nom accessibles :
Utilisation de `<dialog>`, Ajout de `aria-labelledby="dialog-title"` relié à l'id du titre `<h2 id="dialog-title">Réserver {selected}</h2>`


- Le focus doit entrer dans la fenêtre à l’ouverture :
L'appel à la méthode native `dialog.showModal()` déplace automatiquement le focus sur le premier élément interactif à l'intérieur de la modale (le bouton fermer)


- La fermeture doit être possible au clavier et son bouton doit être nommé :
Le `<span>` a été remplacé par  `<button type="button" className="close" aria-label="Fermer">`

- Après la fermeture, le focus doit revenir au déclencheur :
Au clic du bouton "Réserver", on stocke la réf du bouton dans `triggerRef.current`. Lors de l'appel à `closeModal`, `triggerRef.current?.focus()` redonne le focus au bouton du film concerné


- Le contenu derrière la fenêtre ne doit pas participer au parcours pendant son ouverture :
L'ouverture de la balise `<dialog>` avec `.showModal()` rend automatiquement tout le reste du doc ianctif
