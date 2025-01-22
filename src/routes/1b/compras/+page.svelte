<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carrinho de Compras</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }
        .product-list {
            list-style-type: none;
            padding: 0;
        }
        .product-item {
            margin-bottom: 15px;
        }
        .buttons {
            margin-top: 20px;
        }
        .buttons button {
            padding: 10px 20px;
            margin-right: 10px;
            cursor: pointer;
        }
        .summary {
            margin-top: 20px;
        }
    </style>
</head>
<body>

<h1>Carrinho de Compras</h1>

<ul class="product-list">
    <li class="product-item">
        <input type="checkbox" class="product-checkbox" data-price="10.50" data-name="gloss"> gloss - R$ 10,50
    </li>
    <li class="product-item">
        <input type="checkbox" class="product-checkbox" data-price="25.30" data-name="paleta de maquiagem"> paleta de maquiagem - R$ 25,30
    </li>
    <li class="product-item">
        <input type="checkbox" class="product-checkbox" data-price="5.90" data-name="pincel"> pincel - R$ 5,90
    </li>
    <li class="product-item">
        <input type="checkbox" class="product-checkbox" data-price="19.99" data-name="delineado"> delineado - R$ 19,99
    </li>
    <li class="product-item">
        <input type="checkbox" class="product-checkbox" data-price="12.75" data-name="rímel"> rímel - R$ 12,75
    </li>
</ul>

<div class="buttons">
    <button id="select-all">Selecionar Tudo</button>
    <button id="clear-selection">Limpar Seleção</button>
    <button id="finish-purchase">Finalizar Compra</button>
</div>

<div class="summary">
    <h3>Resumo da Compra:</h3>
    <p id="total-items">Total de itens: 0</p>
    <p id="total-price">Valor total: R$ 0,00</p>
    <p id="purchase-summary">Nenhum produto selecionado.</p>
</div>

<script>
    const productCheckboxes = document.querySelectorAll('.product-checkbox');
    const totalItemsElement = document.getElementById('total-items');
    const totalPriceElement = document.getElementById('total-price');
    const purchaseSummaryElement = document.getElementById('purchase-summary');

    // Função para atualizar o resumo da compra
    function updateSummary() {
        let totalItems = 0;
        let totalPrice = 0;
        let selectedProducts = [];

        productCheckboxes.forEach(checkbox => {
            if (checkbox.checked) {
                totalItems++;
                totalPrice += parseFloat(checkbox.getAttribute('data-price'));
                selectedProducts.push(checkbox.getAttribute('data-name') + ' - R$ ' + checkbox.getAttribute('data-price'));
            }
        });

        // Atualiza o total de itens e valor total
        totalItemsElement.textContent = `Total de itens: ${totalItems}`;
        totalPriceElement.textContent = `Valor total: R$ ${totalPrice.toFixed(2)}`;

        // Exibe os produtos selecionados ou uma mensagem de nenhum selecionado
        if (selectedProducts.length > 0) {
            purchaseSummaryElement.textContent = `Produtos selecionados: ${selectedProducts.join(', ')}`;
        } else {
            purchaseSummaryElement.textContent = 'Nenhum produto selecionado.';
        }
    }

    // Eventos para os checkboxes
    productCheckboxes.forEach(checkbox => {
        checkbox.addEventListener('change', updateSummary);
    });

    // Evento para o botão "Selecionar Tudo"
    document.getElementById('select-all').addEventListener('click', () => {
        productCheckboxes.forEach(checkbox => checkbox.checked = true);
        updateSummary();
    });

    // Evento para o botão "Limpar Seleção"
    document.getElementById('clear-selection').addEventListener('click', () => {
        productCheckboxes.forEach(checkbox => checkbox.checked = false);
        updateSummary();
    });

    // Evento para o botão "Finalizar Compra"
    document.getElementById('finish-purchase').addEventListener('click', () => {
        alert(`Compra Finalizada!\nTotal de Itens: ${totalItemsElement.textContent}\nValor Total: ${totalPriceElement.textContent}`);
    });

    // Atualiza o resumo inicial
    updateSummary();
</script>

</body>
</html>
