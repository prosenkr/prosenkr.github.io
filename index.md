
<style>
/* Hide the summary when the details element is open */
details[open] summary {
    display: none;
}

/* Optional: Style the summary to indicate it's clickable */
summary {
    cursor: pointer;
    font-weight: bold;
}

/* Optional: Add some spacing to the paragraph */
details p {
    margin: 10px 0;
}
</style>

<script>
function filterTable(inputId, columnIndex) {
    var input, filter, table, tr, td, i, txtValue;
    input = document.getElementById(inputId);
    filter = input.value.toUpperCase();
    table = document.getElementById("storyTable");
    tr = table.getElementsByTagName("tr");

    for (i = 1; i < tr.length; i++) {  // Start from 1 to skip header
        td = tr[i].getElementsByTagName("td")[columnIndex];
        if (td) {
            txtValue = td.textContent || td.innerText;
            if (txtValue.toUpperCase().indexOf(filter) > -1) {
                tr[i].style.display = "";
            } else {
                tr[i].style.display = "none";
            }
        }       
    }
}
</script>
<table id="storyTable"><table border="1" class="dataframe" id="storyTable">
  <thead>
    <tr>
        <th><input type="text" id="filterStory" onkeyup="filterTable('filterStory', 0)" placeholder="Filter Story"></th>
        <th><input type="text" id="filterBoring" onkeyup="filterTable('filterBoring', 1)" placeholder="Filter Boring"></th>
        <th><input type="text" id="filterFunny" onkeyup="filterTable('filterFunny', 2)" placeholder="Filter Funny"></th>
        <th><input type="text" id="filterCreativityScore" onkeyup="filterTable('filterCreativityScore', 3)" placeholder="Filter Creativity"></th>
        <th><input type="text" id="filterUsefulnessIndex" onkeyup="filterTable('filterUsefulnessIndex', 4)" placeholder="Filter Usefulness"></th>
        <th><input type="text" id="filterNoveltyIndex" onkeyup="filterTable('filterNoveltyIndex', 5)" placeholder="Filter Novelty"></th>
        <th><input type="text" id="filterOwnershipIndex" onkeyup="filterTable('filterOwnershipIndex', 6)" placeholder="Filter Ownership"></th>
    </tr>
    <tr style="text-align: right;">
      <th>STORY</th>
      <th>Boring</th>
      <th>Funny</th>
      <th>CreativityScore</th>
      <th>UsefulnessIndex</th>
      <th>NoveltyIndex</th>
      <th>OwnershipIndex</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>This is a short story.</td>
      <td>1</td>
      <td>3</td>
      <td>5</td>
      <td>7</td>
      <td>9</td>
      <td>11</td>
    </tr>
    <tr>
      <td>\n        <details>\n            <summary>This is a longer story that exceeds the summary character limit set in the function. It should be properly collapsible without duplicating the initial...</summary>\n            <p>This is a longer story that exceeds the summary character limit set in the function. It should be properly collapsible without duplicating the initial characters.</p>\n        </details>\n</td>
      <td>2</td>
      <td>4</td>
      <td>6</td>
      <td>8</td>
      <td>10</td>
      <td>12</td>
    </tr>
    <tr>
      <td>Another short story.</td>
      <td>1</td>
      <td>2</td>
      <td>5</td>
      <td>7</td>
      <td>9</td>
      <td>11</td>
    </tr>
  </tbody>
</table></table>
