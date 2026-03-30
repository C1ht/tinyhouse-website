<script>
  import Button from '$lib/components/ui/buttons.svelte';
</script>

<footer class="border-t border-gray-100 mt-16">
  <div class="max-w-[1280px] mx-auto px-6 py-12">
    
    <!-- top section -->
    <div class="grid grid-cols-1 md:grid-cols-4 gap-10">
      
      <!-- brand -->
      <div class="md:col-span-1 flex flex-col gap-3">
        <a href="/" class="font-bold text-lg">Yderskov</a>
        <p class="text-sm text-muted leading-relaxed">
          Bæredygtige tiny houses bygget med karakter og omtanke.
        </p>
      </div>

      <!-- col 1 -->
      <div class="flex flex-col gap-2">
        <h5 class="font-semibold text-sm mb-1">Firma</h5>
        <a href="/" class="text-sm text-muted hover:text-black transition-colors">Om os</a>
        <a href="/" class="text-sm text-muted hover:text-black transition-colors">Projekter</a>
        <a href="/" class="text-sm text-muted hover:text-black transition-colors">Processen</a>
        <a href="/" class="text-sm text-muted hover:text-black transition-colors">Karriere</a>
      </div>

      <!-- col 2 -->
      <div class="flex flex-col gap-2">
        <h5 class="font-semibold text-sm mb-1">Produkt</h5>
        <a href="/" class="text-sm text-muted hover:text-black transition-colors">Modeller</a>
        <a href="/" class="text-sm text-muted hover:text-black transition-colors">Tilpasning</a>
        <a href="/" class="text-sm text-muted hover:text-black transition-colors">Priser</a>
        <a href="/" class="text-sm text-muted hover:text-black transition-colors">FAQ</a>
      </div>

      <!-- col 3 -->
      <div class="flex flex-col gap-2">
        <h5 class="font-semibold text-sm mb-1">Kontakt</h5>
        <a href="/" class="text-sm text-muted hover:text-black transition-colors">Kontakt os</a>
        <a href="/" class="text-sm text-muted hover:text-black transition-colors">Instagram</a>
        <a href="/" class="text-sm text-muted hover:text-black transition-colors">Facebook</a>
        <a href="mailto:mail@mail.com" class="text-sm text-muted hover:text-black transition-colors">mail@mail.com</a>
      </div>

    </div>

    <!-- bottom bar -->
    <div class="border-t border-gray-100 mt-10 pt-6 flex flex-col md:flex-row justify-between items-center gap-3 text-xs text-muted">
      <span>© 2025 Yderskov. Alle rettigheder forbeholdes.</span>
      <div class="flex gap-4">
        <a href="/" class="hover:text-black transition-colors">Privatlivspolitik</a>
        <a href="/" class="hover:text-black transition-colors">Handelsbetingelser</a>
      </div>
    </div>

  </div>
</footer>