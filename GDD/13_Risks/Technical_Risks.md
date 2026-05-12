\subsection{Riesgos técnicos}

\subsubsection*{Conflictos de fusión en Unity}

Las escenas \texttt{.unity} y los prefabs pueden ser difíciles de fusionar en Git, especialmente cuando varios integrantes modifican los mismos archivos. Esto puede provocar pérdida de trabajo, conflictos extensos o errores difíciles de rastrear.

\textbf{Mitigación.} Cada integrante trabajará en escenas de prueba separadas, por ejemplo \texttt{Level\_Denis} o \texttt{Level\_Dev2}. Solo una persona responsable integrará prefabs probados en la escena principal. Además, se recomienda hacer commits pequeños y frecuentes.

\subsubsection*{Rendimiento}

La instanciación constante de proyectiles, partículas o textos flotantes puede generar caídas de FPS, especialmente durante combates intensos. Este riesgo está documentado en el código observado: uso de \texttt{Instantiate}/\texttt{Destroy} en \texttt{Assets/Scripts/Player.cs} (método \texttt{FireArrow()}) y \texttt{Assets/Scripts/Arrow.cs} (línea \texttt{Destroy(gameObject, 5f)}).

\textbf{Mitigación.} Si las pruebas evidencian problemas de rendimiento, se reemplazará el uso recurrente de \texttt{Instantiate} y \texttt{Destroy} por un sistema de \emph{Object Pooling}. También se revisará el uso de colliders, partículas y actualizaciones por frame.

\subsubsection*{Integración}

Los sistemas de movimiento, combate, enemigos, UI y audio pueden funcionar individualmente pero fallar al integrarse. Este riesgo es común en prototipos con varias áreas de trabajo paralelas y se observa en la base de código actual: múltiples scripts independientes (\texttt{Player.cs}, \texttt{Enemy2.cs}, \texttt{AudioManager.cs}, \texttt{GameManager.cs}) que dependen de managers globales y referencias cruzadas.

\textbf{Mitigación.} Se realizarán integraciones semanales en la rama \texttt{dev}. Cada integración debe probar una escena común con los sistemas principales activos.
