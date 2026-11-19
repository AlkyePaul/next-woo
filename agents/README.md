# Next Woo · Stato del prototipo

## Obiettivo

Questo fork è la nostra base di test per sviluppare ecommerce personalizzati di vario tipo. Usiamo Next.js e Tailwind per la vetrina, con WordPress e WooCommerce per il catalogo, i contenuti, gli ordini e il pagamento. Lo shop di pacchetti turistici è il primo caso d'uso. Il progetto è in fase di prototipo.

## Stato attuale

- Fork di `9d8dev/next-woo` su `AlkyePaul/next-woo`. Il lavoro è sul branch `chore/upgrade-next-woo`.
- Stack aggiornato a Next.js 16.4.6, React 19.3.1, Tailwind CSS 4.3.5 e pnpm 10.30.3. La build di produzione è passata senza uno shop configurato. ESLint ha riportato un avviso su un'immagine.
- Lo shop di riferimento è `https://shop.los7secretos.com`. Le API pubbliche di WordPress e della WooCommerce Store API hanno risposto. L'accesso autenticato al catalogo e il checkout devono ancora essere verificati.

## Sviluppo locale

Il percorso previsto su Windows è `C:\webdev_local\next-woo`. Clonare il fork e selezionare il branch di lavoro. Copiare `.env.example` in `.env.local` e impostare `WORDPRESS_URL` e `NEXT_PUBLIC_WORDPRESS_URL` a `https://shop.los7secretos.com`, e `WORDPRESS_HOSTNAME` a `shop.los7secretos.com`. Configurare le chiavi WooCommerce in `.env.local` o nelle variabili dell'ambiente di deploy. Tenere le credenziali fuori dal repository. Installare con `pnpm install --frozen-lockfile` e avviare con `pnpm dev`.

## Primo caso d'uso · Pacchetti turistici

La vetrina multilingua mostra itinerari, partenze e disponibilità. Il prototipo deve verificare il passaggio della partenza e del numero di viaggiatori al carrello e al checkout nativi di WooCommerce. Oggi lo starter crea ancora un ordine non pagato via API e rimanda alla relativa pagina di pagamento.

Il primo scenario da provare in un ambiente di test è un pacchetto da 1.200 € con un acconto del 30% (360 €) tramite WooCommerce Deposits e un saldo di 840 € richiesto in seguito. Verificare che WooCommerce riservi i posti della partenza corretta e che il saldo non scali nuovamente la disponibilità. Durante la personalizzazione, mantenere i campi specifici dei viaggi separati dal codice condiviso per catalogo e checkout, così la base si può riusare per altri shop.
