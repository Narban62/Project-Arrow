\section{Riesgos y Plan de Mitigacion}

\subsection{Riesgo tecnico: conflictos de fusion en Unity}

Las escenas \texttt{.unity} y los prefabs pueden ser dificiles de fusionar en Git, especialmente cuando varios integrantes modifican los mismos archivos. Esto puede provocar perdida de trabajo, conflictos extensos o errores dificiles de rastrear.

\textbf{Mitigacion.} Cada integrante trabajara en escenas de prueba separadas, por ejemplo \texttt{Level\_Denis} o \texttt{Level\_Dev2}. Solo una persona responsable integrara prefabs probados en la escena principal. Ademas, se recomienda hacer commits pequenos y frecuentes.

\subsection{Riesgo de diseno: scope creep}

El alcance excesivo puede surgir si el equipo intenta crear demasiados niveles, enemigos, mecanicas o sistemas narrativos para el tiempo disponible. Esto puede llevar a una experiencia incompleta y poco pulida.

\textbf{Mitigacion.} Se adopta una filosofia de corte vertical. Es preferible completar un nivel con el cien por ciento de las mecanicas principales funcionando que producir varios niveles vacios o incompletos.

\subsection{Riesgo tecnico: rendimiento}

La instanciacion constante de proyectiles, particulas o textos flotantes puede generar caidas de FPS, especialmente durante combates intensos.

\textbf{Mitigacion.} Si las pruebas evidencian problemas de rendimiento, se reemplazara el uso recurrente de \texttt{Instantiate} y \texttt{Destroy} por un sistema de \emph{Object Pooling}. Tambien se revisara el uso de colliders, particulas y actualizaciones por frame.

\subsection{Riesgo de integracion}

Los sistemas de movimiento, combate, enemigos, UI y audio pueden funcionar individualmente pero fallar al integrarse. Este riesgo es comun en prototipos con varias areas de trabajo paralelas.

\textbf{Mitigacion.} Se realizaran integraciones semanales en la rama \texttt{dev}. Cada integracion debe probar una escena comun con los sistemas principales activos.

\subsection{Riesgo de balance}

Una dificultad mal calibrada puede hacer que el juego resulte frustrante o demasiado simple. Esto afectaria la percepcion de calidad del prototipo.

\textbf{Mitigacion.} Se implementaran variables ajustables para dano, vida, velocidad, recursos y ubicacion de checkpoints. El balance final se realizara durante la fase de QA.

