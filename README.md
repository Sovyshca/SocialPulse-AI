#  SocialPulse AI: SMM Engagement Predictor

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1hFAuBEkSf5qgWOHiQCgM5zZo2cWUY7sb?usp=sharing)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

##  Opis Projektu (Project Description)
**SocialPulse AI** to zaawansowany model uczenia maszynowego, który przewiduje sukces postów w mediach społecznościowych **przed** ich publikacją.
System analizuje parametry takie jak platforma, typ treści, długość tekstu i czas publikacji, aby ocenić szansę na wysokie zaangażowanie (High Engagement).

Projekt demonstruje pełny potok (pipeline) Data Science: od czyszczenia danych po walidację modelu i testy jednostkowe.

##  Jak to działa? (Methodology)
1. **Data Processing:**
   - Czyszczenie danych i obsługa brakujących wartości.
   - Zapobieganie wyciekowi danych (**Data Leakage Prevention**) poprzez usunięcie kolumn `likes`, `views` ze zbioru treningowego.
2. **Model:**
   - Algorytm: **Random Forest Classifier**.
   - Optymalizacja: **GridSearchCV** do znalezienia najlepszych hiperparametrów.
3. **Ewaluacja:**
   - Raport klasyfikacji (Precision, Recall, F1-Score).
   - Macierz pomyłek (Confusion Matrix).

##  Jak uruchomić (Installation & Usage)

Projekt został zoptymalizowany do pracy w **Google Colab**, ale działa również lokalnie.

### Opcja A: Szybki start w chmurze (Zalecane)
Kliknij przycisk **Open in Colab** na górze strony lub użyj tego linku:
[Uruchom w Google Colab](https://colab.research.google.com/drive/1hFAuBEkSf5qgWOHiQCgM5zZo2cWUY7sb?usp=sharing)
W bloku "GŁÓWNA LOGIKA PROGRAMU (MAIN)" usuń "." w input_csv_path i output_model_path
 ```bash
   input_csv_path = './content/social_media_engagement_dataset.csv' -> input_csv_path = '/content/social_media_engagement_dataset.csv'
   output_model_path = './content/model_social_media.pkl' -> output_model_path = '/content/model_social_media.pkl'
   output_regression_model_path = './content/regression_model_social_media.pkl' -> output_regression_model_path = '/content/regression_model_social_media.pkl'
 ```    

> **Uwaga:** Po uruchomieniu notatnika pamiętaj, aby wgrać plik `social_media_engagement_dataset.csv` do sesji (panel po lewej stronie).

---

### Opcja B: Uruchomienie w VS Code
Jeśli wolisz pracować na własnym komputerze:


1. **Sklonuj repozytorium:**
```bash
   git clone https://github.com/Sovyshca/SocialPulse-AI.git
```
 2. **Zainstaluj wymagane biblioteki:**
```bash
   # Tworzenie wirtualnego środowiska
   python -m venv .venv

   # Aktywacja środowiska
   source .venv/bin/activate

   # Instalacja ipykernel (wymagane przez VS Code) oraz wymagań projektu
   pip install ipykernel
   pip install -r requirements.txt
```      

### Struktura Projektu

UM_w_Python.ipynb - Główny plik z kodem, analizą i modelem.

requirements.txt - Lista wymaganych bibliotek Python.

README.md - Dokumentacja projektu.

(Plik social_media_data.csv powinien znajdować się w głównym katalogu)

Testy Jednostkowe (Unit Tests)
W projekcie zaimplementowano klasę TestSocialMediaProject, która automatycznie sprawdza:

Czy target (is_successful) jest poprawnie tworzony.

Czy usunięto zmienne powodujące wyciek danych (likes, shares).

Czy podział na zbiory treningowe/testowe jest poprawny logicznie.