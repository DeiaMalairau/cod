# cod
Lab5

echo"<h1>-----Practică-----</h1>";

//Ex1

 echo"<h4>Exercițiul 1</h4>";
  $arr = array (2, 4, 5, 7, 8, 9, 10);
   print_r($arr);

//a
   echo "<p>Elementul minim: " .min($arr). "</p>";
//b
   echo "<p> Minimumul: ".min(array(2, 4)). "</p>";
   echo "<p> Maximumul: ".max(array(2, 4)). "</p>";
//c
$arrsort = array_values($arr);
sort ($arrsort);
echo "<p> Tabelul este ordonat crescător: ",($arrsort = $arr) ? 'Adevărat' : 'Fals', "</p>";
//d
$suma = 0;
$nrmedia = 0;
  for ($i = 1; $i < sizeof($arr); $i+= 2) {
    $suma += $arr[$i];
    $nrmedia++;
  }
  echo "<p> Media elementelor pozitive pe poziție impară: " .$suma/$nrmedia. "</p>";
//e

//f
for ($i = 1; $i < sizeof ($arr); $i++) {
  $p = $i;
  while ($p > 0 && $arr[$p] > $arr[$p-1]) {
    $aux = $arr[$p];
    $arr[$p] = $arr[$p-1];
    $arr[$p-1] = $aux;
    $p--;
  }
}

  echo "<p> Ordonarea desrescătoare prin inserție: ";
  print_r($arr);
//g
 $b = array ();
    for ($i = 0; $i<99; $i++)
       $b[] = 0;

    foreach ($arr as $val)
      $b[$val]++;

    $arrsort = array();
    for ($i = 0; $i < 99; $i++) {
      if ($b[$i] > 0) {
        $arrsort[] = $i;
      }
    }
     echo "<br/>Ordonarea crescătoare prin numărare: ";
     print_r($arrsort);
//h
$value = 5;
echo "<p> Tabloul conține valoarea ", $value, ": " ,(in_array($value, $arr))?"Da":"Nu","</p>";
//i
echo "<p> Tabloul este o mulțime: ", (sizeof($arr) == sizeof(array_unique($arr)))?"Da":"Nu", "</p>";
//j


//Ex2

echo "<h4>Exercițiul 2</h4>";
$x = array (1, 6, 3, 2);
$y = array (3, 5, 6, 4);
echo "<p> Array-ul X: ";
print_r($x);
echo "</p>";

echo "<p> Array-ul Y: ";
print_r($y);
echo "</p>";

//a
 if (sizeof($x) == sizeof($y)) {
   $s = 0;
   for ($i = 0; $i < sizeof($x); $i++) {
     $s+=($x[$i] * $y[$i]);
      }
   echo "<p> Suma = ",$s,"</p>";

 } else {
   echo "<p> Tabelele nu au aceeași lungime! </p>";
 }
//b,c
  if (sizeof($x) == sizeof(array_unique($x)) && sizeof($y) == sizeof(array_unique($y))) {
    echo "<p> Intersecția: ";
    $intersect = array_intersect ($x, $y);
    print_r($intersect);
    if (sizeof($intersect) == 0) {
      echo "Nu sunt elemente comune!";
    }
    echo "</p>";


   $reuniune = array_unique(array_merge($x, $y));
   echo "<p> Reuniunea: ";
   print_r($reuniune);
   echo "</p>";

 } else {
   echo "<p> Nu sunt mulțimi!";
 }
 //d
 $intersect = array_intersect($x, $y);
 echo "<p> Numărul de elemente din Y ce apar în X: ", sizeof($intersect),"</p>";
//e
$i = 0;
$aux = false;

  foreach ($y as $valy) {
    if ($x[$i] == $valy){
      $i++;
    } else {
      $i = 0;
    }
    if ($i == sizeof($x)){
      $aux = true;
      break;
    }
  }
  echo "<p> Tabloul X este un subșir în Y: ", ($aux)?"Da":"Nu","</p>";
//f

 sort($x);
 sort($y);

 echo "<p> X sortat: ";
 print_r($x);
 echo "</p>";

 echo "<p> Y sortat: ";
 print_r($y);
 echo "</p>";

  $i = 0;
  $j = 0;
  $interclass = array();
  while ($i < sizeof ($x) && $j < sizeof($y)) {
    if ($x[$i] >= $y[$j]){
      $interclass[] = $y[$j];
      $j++;
    } else {
      $interclass[] = $x[$i];
      $i++;
    }
  }

  echo "<p> Interclasarea : ";
  print_r($interclass);
  echo "</p>";
