from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier

# Carrega o dataset
iris = load_iris()
X = iris.data
y = iris.target

# Divide os dados em treino e teste
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Cria e treina o modelo
knn = KNeighborsClassifier(n_neighbors=3)
knn.fit(X_train, y_train)

# Faz previsões
y_pred = knn.predict(X_test)

# Avalia o modelo
from sklearn.metrics import accuracy_score
print("Accuracy:", accuracy_score(y_test, y_pred))
