# Karbon-Ayak-zi-Hesaplama-
def calculate_carbon_footprint():
  print("Karbon ayak izini hesaplayalım!")

  # Ask for user input
  electricity_consumption = float(
      input("Lütfen aylık yakıt miktarınızı girin (kWh):  "))
  gas_consumption = float(
      input("Aylık metre küp cinsinden doğalgaz tüketiminiz, girin (m3):  "))
  miles_driven = float(
      input("Aylık şahsi araç ile yolculuk miktarınızı girin (mil):  "))
  public_transport_distance = float(
      input("Aylık toplu taşımada gittiğiniz yol uzunluğunu girin (km):   "))
  flights_distance = float(
      input(
          "aylık iç hat uçuş yolculuğunuzda toplam yol uzunluğunu girin (km):  "
      ))
  diet_choice = input("Beslenme şekliniz nedir? (vegan, vejetaryan, etçil):")
  waste_recyling = input("Geri dönüşüm yapıyor musun: ")
  cargo_services = float("Aylık evinize gelen kargo sayısı kaçtır? : ")
  shower_times = float("aylık duş sayınız kaçtır?")
  toilet_flush_times = float("aylık tuvalet sifonuna kaç kere basıyorsunuz? ")
  clothes_washing_frequency = float("ayda kaç kere çamaşır yıkıyorsunuz? ")
  dishes_frequency = float("ayda kaç kere bulaşık yıkıyorsunuz? ")
  garbage_product = float("aylık çöp üretim miktarınız kaçtır? ")
  clothes_shoppings = float("aylık yeni kıyafet alımınız ne kadar ")
  packaging_consumption = float("aylık ambalajlı ürün tüketimiz ne kadar? ")
  electronic_devices_consumption = float(
      "aylık elektronik cihazlarınızın kullanım miktarı kaçtır? ")
  coal_using = input("aylık kömür yakıyor musunuz? ")
  air_conditioning = input("Klima kullanıyor musunuz? ")
  home_cleaning = float("Haftada kaç kez evinizi temizliyorsunuz? ")
  use_of_deodorant = float("Haftada kaç kez deodorant kullanıyorsunuz? ")
  watering = float("Haftada kaç kez bahçe suluyorsunuz? ")
  number_of_domestic = float("evde kaç kişi var? ")
  dishes_byhand = input("elde bulaşık yıkıyor musunuz? ")
  walking = float("ayda kaç km yürüyorsunuz? ")
  led_light = input("Evinizde LED ampül kullanıyor musunuz?")

  # Define emission factors (values are approximate)
  electricity_emission_factor = 0.8  # kg CO2 per kWh
  gas_emission_factor = 2.0  # kg CO2 per cubic meter
  car_emission_factor = 0.2  # kg CO2 per mile
  public_transport_emission_factor = 0.1  # kg CO2 per mile
  flight_emission_factor = 0.2  # kg CO2 per mile
  water_emission_factor = 0.5  # kg CO2 per gallon
  garbage_emission_factor = 0.8  # ton CO2 per ton
  clothes_shopping_emission_factor = 20
  packaging_emission_factor = 0.5  # ton CO2 per ton
  coal_emission_factor = {
      'yes': 0.82,
      'no': 2.0,  #default if coil is not used. gas is used
  }
  diet_emission_factors = {
      'vegan': 1.5,  # kg CO2 per meal
      'vegetarian': 2.5,  # kg CO2 per meal
      'meat-based': 3.5  # kg CO2 per meal
  }
  deodorant_emission_factor = 0.5  # kg CO2 per bottle

  # Calculate carbon footprint for each category
  electricity_footprint = electricity_consumption * electricity_emission_factor
  gas_footprint = gas_consumption * gas_emission_factor
  car_footprint = miles_driven * car_emission_factor
  public_transport_footprint = public_transport_distance * public_transport_emission_factor
  flight_footprint = flights_distance * flight_emission_factor
  diet_footprint = diet_emission_factors.get(
      diet_choice.lower(), 2.5)  # Default to vegetarian if input is invalid

  # Calculate total carbon footprint
  total_footprint = electricity_footprint + gas_footprint + car_footprint + public_transport_footprint + flight_footprint + diet_footprint

  print(
      "\nYour estimated carbon footprint is: {:.2f} kg CO2 equivalent per month"
      .format(total_footprint))


# Run the function
calculate_carbon_footprint()
