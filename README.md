class Imovel {
  double areaConstruida;

  Imovel(this.areaConstruida) {
    if (areaConstruida < 0) {
      throw ArgumentError("A área construída não pode ser negativa.");
    }
  }

  double get iptu {
    if (areaConstruida == 0) {
      return 300;
    } else if (areaConstruida <= 50) {
      return 500;
    } else if (areaConstruida <= 100) {
      return 800;
    } else if (areaConstruida <= 200) {
      return 1200;
    } else {
      return 2000;
    }
  }
}

void main() {
  var imovel = Imovel(120);

  print("Área construída: ${imovel.areaConstruida.toStringAsFixed(2)} m²");
  print("Valor do IPTU: R\$ ${imovel.iptu.toStringAsFixed(2)}");
}
