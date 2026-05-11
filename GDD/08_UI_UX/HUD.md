\section{Interfaz de Usuario: HUD}

\subsection{Diseno general}

El HUD se construye en un \texttt{Canvas} configurado en modo \emph{Scale With Screen Size}. Esta configuracion evita deformaciones y permite que la interfaz conserve proporciones adecuadas en diferentes resoluciones de pantalla.

\subsection{Elementos principales}

En la esquina superior izquierda se ubica la informacion vital del jugador. La salud se representa mediante iconos de corazones usando componentes \texttt{UI Image}, acompanados por un contador numerico cuando sea necesario. Cerca de esta zona se muestra el contador de Diamantes de Almas.

\subsection{Textos flotantes de dano}

Cuando un enemigo recibe dano, se instancia un prefab de texto en el espacio del mundo o en un Canvas asociado. Este texto flota hacia arriba y se desvanece progresivamente mediante reduccion del valor alfa. La animacion puede implementarse con un \texttt{Animator}, una corrutina o un sistema de tweening si el proyecto incorpora una libreria externa.

\subsection{Criterios de claridad}

La interfaz debe ser legible sin ocupar espacio excesivo. Los indicadores deben comunicar informacion esencial y evitar distracciones durante combate o plataformas. La estetica debe integrarse con el tono del juego mediante bordes, iconografia y colores coherentes con la fantasia gotica.

