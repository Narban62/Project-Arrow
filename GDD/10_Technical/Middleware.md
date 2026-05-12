\subsection{Middleware}

\subsubsection*{Definición}

En el contexto de este proyecto Unity, entendemos por "middleware" a los componentes o servicios intermedios que medían la comunicación entre los elementos de juego y las capas de presentación/entorno: gestores de escena, gestores de audio, sistemas de estado de juego y adaptadores de terceros que actúan como capa de servicio centralizada.

\subsubsection*{Middleware en el juego}

Los artefactos que cumplen esta función en el juego incluyen, entre otros:
\begin{itemize}
  \item \textbf{`GameManager`}: presente en \texttt{Assets/Scripts/GameManager.cs} — controla estado global, transiciones y lógica de alto nivel.
  \item \textbf{`AudioManager` / `Sound`}: presentes en \texttt{Assets/Scripts/AudioManager.cs} y \texttt{Assets/Scripts/Sound.cs} — encapsulan reproducción de efectos y sonidos y mantienen fuentes de audio (AudioSources) por clip/sonido.
  \item \textbf{`SceneManagement`}: presente en \texttt{Assets/Scripts/SceneManagement.cs} — orquesta carga/recarga de escenas y opciones de menú (en el código se usan cadenas de escena como "SampleScene" y "Menu").
  \item \textbf{Librerías y utilidades de terceros}: por ejemplo \texttt{Assets/LeanTween/} — usado por scripts como \texttt{Assets/Scripts/Saw.cs} y \texttt{Assets/Scripts/GameManager.cs} para animaciones y transiciones, funcionando como una capa de servicio para interpolaciones.
\end{itemize}

\subsubsection*{Responsabilidades}

Los componentes de middleware cumplen las siguientes responsabilidades observadas:
\begin{itemize}
  \item Centralizar la reproducción de audio y la configuración de volúmenes (\texttt{AudioManager}).
  \item Mantener el estado global del juego y orquestar eventos de alto nivel (\texttt{GameManager}).
  \item Gestionar la navegación entre escenas y operaciones de reinicio/pausa (\texttt{SceneManagement}).
  \item Proveer utilidades de interpolación y temporización a otros sistemas (\texttt{LeanTween}).
\end{itemize}