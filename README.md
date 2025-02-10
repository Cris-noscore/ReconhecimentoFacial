##Reconhecimento Facial com FaceNet e MTCNN
Este projeto implementa um sistema básico de reconhecimento facial usando o modelo FaceNet pré-treinado e o detector de faces MTCNN. As bibliotecas principais utilizadas incluem TensorFlow, OpenCV, e NumPy.

#Instruções de Instalação
Certifique-se de ter o ambiente Python configurado. Instale as dependências necessárias usando o seguinte comando:

pip install mtcnn tensorflow opencv-python numpy

#Uso
O projeto inclui funções para detectar faces, extrair embeddings faciais e reconhecer rostos com base em um banco de dados de faces conhecidas. Abaixo está um resumo de como utilizá-las.

1. Detectar Faces
A função detect_faces(image) utiliza MTCNN para detectar e recortar faces em uma imagem. As faces detectadas são redimensionadas para o tamanho esperado pelo modelo FaceNet.

2. Extrair Embeddings Faciais
Use a função get_embedding(face_image) para obter um vetor de características (embedding) a partir de uma imagem de rosto. Este vetor é gerado pelo modelo FaceNet e é usado para comparação de similaridade entre diferentes rostos.

3. Criar Banco de Dados de Faces Conhecidas
Você pode adicionar faces conhecidas ao banco de dados usando add_known_face(name, image). Esta função detecta a face na imagem fornecida, gera o embedding e armazena-o associado ao nome dado.

4. Reconhecer Faces
Para reconhecer uma face, utilize a função recognize_face(image). Ela detectará as faces na imagem fornecida, calculará o embedding de cada uma, e comparará com o banco de dados de faces conhecidas para identificar possíveis correspondências.

Exemplo de Uso

# Carregar imagens
img1 = cv2.imread('jimCarrey.jpg')  # Imagem de um rosto conhecido
img2 = cv2.imread('jimCarrey2.jpg')  # Outra imagem para teste de reconhecimento

# Adicionar rosto conhecido
add_known_face("Jim Carrey", img1)

# Testar reconhecimento facial
recognize_face(img2)

Certifique-se de fornecer os caminhos corretos para as imagens jimCarrey.jpg e jimCarrey2.jpg, que devem estar no mesmo diretório ou ajustar o caminho de acordo.

Notas
Ajuste o limiar de decisão (distance < 0.5) na função recognize_face conforme necessário.
A eficácia do reconhecimento facial pode variar dependendo da qualidade e características das imagens fornecidas.
