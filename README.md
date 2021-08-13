<script>
    $("#dt_nascimento").mask("99/99/9999", {
    completed: function () {
        console.log('complete')
        var value = $(this).val().split('/');
        var maximos = [31, 12, 2100];
        var novoValor = value.map(function (parcela, i) {
            if (parseInt(parcela, 10) > maximos[i]) return maximos[i];
            return parcela;
        });
        if (novoValor.toString() != value.toString()) $(this).val(novoValor.join('/')).focus();
    }
});
</script>
