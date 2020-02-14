$RandomNumber = Random(1, 100, 1)

$msg = MsgBox(4, "[GAME] Plus ou Moins by SKZ", "Bienvenue au jeu du Plus ou du Moins."& @CRLF & @CRLF & _
				  "Le but du jeu :" & @CRLF & @CRLF & _
				  "Je vais choisir un nombre aléatoirement, vous devez le trouver. Je vous donnerai les indications 'plus' ou 'moins' pour vous aider. "& @CRLF & @CRLF & _
				  "Vous êtes prêt ?")
If $msg = 7 Then _close()

Func _close()
        MsgBox(0,"[GAME] Plus ou Moins by SKZ","Merci d'avoir essayé ce mini-jeu ! ♥")
        Exit
EndFunc

Do
   $reponse = InputBox("[GAME] Plus ou Moins by SKZ", "Choisissez un nombre entre 0 et 100.")
   If @error Then _close()

   $reponse = Number($reponse)

   if ($reponse < 0 or $reponse > 100) Then
	  MsgBox(0, "[GAME] Plus ou Moins by SKZ", "Le nombre doit être compris entre 0 et 100.")
   Else
	  If ($reponse > $RandomNumber) Then
			MsgBox(0, "[GAME] Plus ou Moins by SKZ", "Moins ! ("&$reponse&")")
	  ElseIf ($reponse < $RandomNumber) Then
			MsgBox(0, "[GAME] Plus ou Moins by SKZ", "Plus ! ("&$reponse&")")
	  EndIf
   EndIf

Until ($reponse = $RandomNumber)
MsgBox(0, " [GAME] Plus ou Moins by SKZ", "Bien joué ! Merci d'avoir essayé ce mini-jeu ! ♥")
