# -Return-objConnection.Execute-USE-varInitalCatalog-Else-Return-1-EndIf
     Return $objConnection.Execute("USE " &amp; $varInitalCatalog)     Else         Return 1     EndIf EndFunc  Func _OpenRecordset($varTable,$arrSelectFields,$arrWhereFields=0,$varCursorType=$adOpenForwardOnly,$varLockType=$adLockReadOnly)     If Not IsObj($objConnection) Then Return -1     If Not IsObj($objRecordSet) Then Return -2     $strOpen = "SELECT "     $varFieldCount = UBound($arrSelectFields)-1     For $x = 0 to $varFieldCount         $strOpen &amp;= "[" &amp; $arrSelectFields[$x] &amp; "]"         If $x &lt; $varFieldCount Then $strOpen &amp;= ", "     Next     $strOpen &amp;= " FROM " &amp; $varTable     If IsArray($arrWhereFields) Then         $strOpen &amp;= " WHERE "         $varFieldCount = UBound($arrWhereFields)-1         For $x = 0 to $varFieldCount             $strOpen &amp;= $arrWhereFields[$x]
