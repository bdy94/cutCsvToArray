function cutCsvToArray($file, $nbr){
    $csv = file_get_contents($file);
    $newKeyArray = str_replace('"', '', $csv);
    $csv = str_replace(',', ';', $newKeyArray);
    $separatorCsv = ";";

    $row = explode("\n", $csv); //separe les lignes
    $firstRow = trim($row[0]); //premiere ligne pour creer les keys du array
    $keys = explode($separatorCsv, $firstRow);
    $fileLines=file($file);
    $countLines = count($fileLines);
    if ($countLines > $nbr) {
        $startArray = $countLines - $nbr;
    } else {
        $startArray = 1;
    }
    $array = [];
    for ($i=$startArray; $i <= $countLines-1; $i++) { 
        $secondRow = $row[$i];
        $values = explode($separatorCsv, $secondRow);
        $array[] = array_combine($keys, $values);
    }
    return $array;
}
