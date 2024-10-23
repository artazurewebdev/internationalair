import streamlit as st
from datetime import datetime
import time

st.sidebar.image("jetpicture1.png")
st.sidebar.title("InternationalAir")
st.sidebar.subheader("The best way to travel")

pageselect = ["Home", "InternationalAir", "HyperJets"]
pagechoice = st.sidebar.selectbox("Select Page", pageselect)

if pagechoice == "Home":
    st.title("InternationalAir")

if pagechoice == "InternationalAir":
    st.title("InternationalAir Commercial")

    commercialaircrafts = {
        "Boeing 737-MAX"
        "Boeing 737-MAX 8"
        "Boeing 737-MAX 10"
        "Comac C919"
        "Airbus A320"
        "Airbus A321"
        "Airbus A220"
        "Boeing 757"
        "Boeing 767"
        "Boeing 777"
        "Boeing 787 Dreamliner"
        "Boeing 797"
        "Boeing 747"
        "Airbus A380"
    }

if pagechoice == "HyperJets":

    aircrafts = {
        "Beechcraft Hawker 400XP": 3500, 
        "Cessna Citation CJ2": 3750, 
        "HondaJet": 3250, 
        "Embraer Phenom 300": 3750, 
        "Embraer Phenom 300/E": 3750,
        "Beechcraft Hawker 800": 3500, 
        "Pilatus PC-24": 3300,
        "Bombardier Learjet 60": 3600, 
        "Bombardier Learjet 75": 4000,
        "Gulfstream G400": 3400, 
        "Gulfstream G500": 3500,
        "Gulfstream G600": 3750,
        "Gulfstream G700": 4000,
        "Gulfstream G800": 3900,
        "Cessna Citation XLS": 3600, 
        "Cessna Citation Ascend": 3500, 
        "Cessna Citation Sovereign": 3750,
        "Bombardier Challenger 350": 3600, 
        "Cessna Citation X": 3700, 
        "Cessna Citation Latitude": 3450,
        "Dassault Falcon 6X": 4250,
        "Embraer Praetor 500": 3600,
        "Gulfstream G280": 3900, 
        "Cessna Citation Longitude": 3750, 
        "Bombardier Challenger 350/3500": 3600, 
        "Bombardier Challenger 604": 3750, 
        "Embraer Legacy 600": 4250,
        "Dassault Falcon 900LX": 4250, 
        "Gulfstream G-IVSP": 3800, 
        "Bombardier Global 7500": 4500, 
        "Bombardier Challenger 650": 3750,
        "Dassault Falcon 8X": 4650,
        "Gulfstream G650ER": 3750, 
        "Gulfstream G550": 3750, 
        "Dassault Falcon 2000LXS": 4000,
        "Bombardier Global 5500": 4500, 
        "Bombardier Global 6000": 4600,
        "Dassault Falcon 10X": 4750,
        "Comac C919": 20000,
        "Airbus A320": 22000,
        "Boeing 737-900":24500,
        "Boeing 737-MAX": 25000, 
        "Boeing 797": 27500,
        "Bombardier CRJ1000": 21000,
        "Boeing 777, HyperJets Emerald Aircraft": 30000,
        "Boeing 747-8i, HyperJets Diamond Aircraft": 40000,
        "Scaled Composites VSS Unity Hypersonic Jet": 500000
    }

    destinations = [
        "North America", "South America", "Europe", "Asia", "Australia"
    ]

    st.title("HyperJets Private Jet Charter")
    st.text("Presented by InternationalAir")

    st.subheader("Flight Amenities")
    st.write("Lightning-fast WiFi")
    st.write("1 Meal per 4 hours of flight time. At least 1 meal will be provided per flight")
    st.write("Complimentary Transit up to 50 miles from airport")
    st.write("On-demand Flight Attendants")

    st.subheader("Book a Flight")

    privatehistory = [
        "Yes",
        "No"
    ]

    st.text_input("Full Name")
    st.number_input("Age", min_value=18)
    st.selectbox("Have you flown private before?", privatehistory)
    contact_ph = st.number_input("Contact Phone Number", min_value=000000000000)
    contactemail = st.text_input("Contact Email")

    st.subheader("Select Aircraft")

    # Aircraft selection
    selected_aircraft = st.selectbox("Choose your aircraft", aircrafts)
    st.write(f"You have selected: **{selected_aircraft}**")

    st.subheader("Select Destinations")

    # Departure and arrival airports
    departure_airport = st.text_input("Enter departure airport (three letter code):")
    arrival_airport = st.text_input("Enter arrival airport (three letter code):")

    yesnoint = [
        "No",
        "Yes, I have valid visa for the country I am visiting",
        "Yes, I do not have valid visa for the country I am visiting",
    ]

    international = st.selectbox("Is your flight international?", yesnoint)

    if international == ("Yes, I do not have valid visa for the country I am visiting"):
        st.error("A valid visa is required for traveling internationally. Custom policies are the same, even when flying private. Traveling internationally unauthorized is illegal.")
        internationaltravelfee = 0
    if international == ("No"):
        internationaltravelfee = 0

    leave_date = st.date_input("Select departure date")
    leave_time = st.time_input("Select departure time")

    # Flight time input
    flight_hours = st.number_input("Enter estimated flight time (hours, one-way)", min_value=1)
    st.write(f"Estimated one-way flight time: **{flight_hours} hours**")

    # Round trip question
    is_round_trip = st.radio("Is this a round trip?", ("Yes", "No"))

    # Round trip return time
    if is_round_trip == "Yes":
        return_date = st.date_input("Select return date")
        return_time = st.time_input("Select return time")

    st.subheader("Passengers")

    # Passenger and baggage details
    num_passengers = st.number_input("Enter number of passengers", min_value=1)
    num_checked_bags = st.number_input("Enter number of checked-in bags", min_value=0)
    num_carryon_bags = st.number_input("Enter number of carry-on bags", min_value=0)

    st.subheader("Amenities")

    amenities = {
        f"7G Wi-Fi | $100": 100,
        f"In-flight Chef | $1200": 1200,
        f"Pet Luxury Set for Cats | $800": 800,
        f"Pet Luxury Set for Dogs | $800": 800,
        f"Onboard NetFlix Access | $15": 15,
        f"Onboard Hulu Access | $15": 15,
        f"Onboard Peacock Access | $15": 15,
        f"Onboard Disney+ Access | $15": 15,
        f"Custom HyperJets iPhone 16 | $1500": 1500,
        f"Custom HyperJets Matte Sticker Set | $5": 5
    }

    # Amenities selection
    selected_amenities = st.multiselect("Select additional amenities", amenities.keys())

    express = {
        "No Transit Required": 0,
        "Vehicle | Available Standard Sedan: Complimentary | Up to 4 Seats": 0,
        "Premium Vehicle | Available Sedan: $50 | Up to 4 Seats": 50,
        "Vehicle | Available SUV: Complimentary | 6-8 Seats ": 0,
        "Premium Vehicle | Available SUV: $75 | 6-8 Seats": 75,
        "Premium Vehicle | BMW X-7: $100 | Up to 7 Seats": 100,
        "Premium Vehicle | Lamborghini Urus: $1000 | 4-5 Seats": 1000,
        "Premium Vehicle | Rolls Royce Ghost: $1500 | Up to 5 Seats": 1500
    }

    st.subheader(f"Transit")

    with st.expander("Vehicle Catalog"):
        st.success("If you are booking early enough, you can write a preferred vehicle in the special requests of this form, and the vehicle may be reserved for you.")
        st.write("All vehicles in the catalog are owned, maintained, and regulated by HyperJets")
        st.markdown("<u>**Standard Sedans**</u>", unsafe_allow_html=True)
        st.write("2025 Nissan Sentra")
        st.write("Honda Civic")
        st.write("Hyundai Sonata")
        st.write("Volkswagen Passat")
        st.write("Toyota Corolla")
        st.write("Toyota Camry")
        st.write("Toyota Mirai")
        st.markdown("<u>**Premium Sedans**</u>", unsafe_allow_html=True)
        st.write("Audi A7")
        st.write("BMW 7-Series")
        st.write("Mercedes-Benz E-Class")
        st.write("Lucid Air")
        st.write("BMW i4")
        st.markdown("<u>**Standard SUVs**</u>", unsafe_allow_html=True)
        st.write("Toyota Highlander")
        st.write("GMC Terrain")
        st.write("Volkswagen Tiguan")
        st.write("Buick Enclave")
        st.write("Toyota RAV-4")
        st.write("Tesla Model Y")
        st.write("Hyundai Tucson")
        st.markdown("<u>**Premium SUVs**</u>", unsafe_allow_html=True)
        st.write("Tesla Model Y")
        st.write("BMW X-7")
        st.write("BMW X-5")
        st.write("Mercedes-Benz GLE")
        st.write("Tesla Cybertruck")

    with st.expander("Premium Vehicle Complimentary Treats"):
        st.write("Ghirardelli Assorted Chocolates"),
        st.write("Assorted Truffle Chips"),
        st.write("Lays Truffle Chips"),
        st.write("Assorted Lays Chips")
        st.write("Assorted Oreos")

    with st.expander("Transit Information"):
        st.write("The selected type of transportation will be immediately outside the aircraft after landing, or a HyperJets flight attendant will direct you to your vehicle.")
        st.write("Tips are not required, unless the transit that you chose is a complimentary type of transit")
        st.write("Catering is not provided on the ride. But on premium vehicles, complimentary snacks and treats are available.")

    convoy_type = st.selectbox("Select Type of Transit", express)
    st.text_input("Address of location to arrive at")

    st.subheader("Complimentary Meal")

    with st.expander("See Food Options"):
        st.success("One complimentary meal is provided per 4 hours of flight time")
        st.write("At least one meal is provided per flight")
        st.write("Meals are provided from RelaxDelicacy")
        st.write("All meals are available at any time")
        st.warning("Please specify meat temperatures. Default is medium-rare")
        st.write("If you would like extra meals outside of the complimentary ones, specify in the special requests and the price will be applied onto your quote. Meals can cost up to $25")
        st.markdown("<u>**Breakfast**</u>", unsafe_allow_html=True)
        st.write("American Breakfast: Scrambled Pepper Eggs, Bacon, Butter Pancakes w/ Maple Syrup")
        st.write("French Strawberry Crepes: Crepes, Strawberry Syrup")
        st.write("French Chocolate Banana Crepes: Crepes, Banana, Chocolate Syrup")
        st.write("Breakfast Tacos: Corn or Wheat Tortilla, Chorizo, Pepper Eggs, Ground Beef, Scallions")
        st.write("Deluxe Cereal: Oats, Raisins, Strawberries, Bananas, Blueberry, Creme Syrup, Milk")
        st.markdown("<u>**Lunch**</u>", unsafe_allow_html=True)
        st.write("Grilled Cheese: Cheddar Cheese, Mayonnaise, Sour Cream, White Bread")
        st.write("Pizza: Cheese Pizza, Pepperoni Pizza, Sausage Pizza, 3 Slices")
        st.write("Sushi Package: Salmon Nigiri, Avocado Roll, Salmon Roll, Salmon Sashimi")
        st.markdown("<u>**Dinner**</u>", unsafe_allow_html=True)
        st.write("Gateway Burger: Beef Patty, Onion Rings, Lettuce, Tomatoes, BBQ Sauce")
        st.write("Lemon Pepper Steak: Steak, Lemon, Pepper Sauce, Rosemary")
        st.write("Tonkotsu Ramen: Ramen Noodles")
        st.write("Vietnamese Pho: Rice Noodle, Spices")
        st.write("Sushi Dinner: Tonkotsu Ramen, Salmon Nigiri, Avocado Roll, Salmon Roll")
        st.markdown("<u>**Appetizers/Sides**</u>", unsafe_allow_html=True)
        st.write("Fries")
        st.write("Nacho Fries: Fries, Salsa, Guacamole, Cheddar Cheese, Ground Beef, Garlic Seasoning")
        st.write("Ceviche")
        st.write("Cucumber Salad: Cucumber, Sa Te Sauce, MsG, Chili Oil, Garlic, Spice Package")
        st.markdown("<u>**Dessert**</u>", unsafe_allow_html=True)
        st.write("Vanilla Cake")
        st.write("New York Cheesecake")
        st.write("Italian Banana Bread")
        st.write("English Shortbread")
        st.write("Strawberry Poundcake")
        st.markdown("<u>**Drinks**</u>", unsafe_allow_html=True)
        st.write("Water")
        st.write("1% Milk")
        st.write("Bubble Tea: Choice of Sugar, Choice of Ice")

    st.text_input("Please write down your food choices.")

    if st.text_input("Special Requests"):
        st.warning("Special Requests will not be regarded with a direct credit card payment on this website")

    if st.text_input("Special Catering for dishes not on the menu"):
        st.warning("Special catering requires evaluation to fulfill. Email quotes will be required. Not complimentary.")

    price_per_hour = aircrafts[selected_aircraft]
    piloting_fees_per_hour = 1000
    gate_and_boarding_fees = 1000
    passenger_fee = 750
    checked_bag_fee = 50
    carryon_bag_fee = 125
    transportation_cost = express[convoy_type]

    # Calculate total amenity cost
    amenity_cost = sum(amenities[amenity] for amenity in selected_amenities)

    # Calculate total flight hours
    total_flight_hours = flight_hours * 2 if is_round_trip == "Yes" else flight_hours

    if selected_aircraft == ("Scaled Composites VSS Unity Hypersonic Jet"):
        passenger_fee = 300000
        st.info("To charter the VSS Unity, booking must be at least 6 months in advance")

    if selected_aircraft == ("Boeing 777, HyperJets Emerald Aircraft"):
        passenger_fee = 1500

    if selected_aircraft == ("Boeing 747, HyperJets Diamond Aircraft"):
        passenger_fee = 2000

    if international == ("Yes, I have valid visa for the country I am visiting"):
        internationaltravelfee = 100

    # Calculate total cost components
    flight_cost = price_per_hour * total_flight_hours
    piloting_cost = piloting_fees_per_hour * total_flight_hours
    passenger_cost = passenger_fee * num_passengers
    baggage_cost = (num_checked_bags * checked_bag_fee) + (num_carryon_bags * carryon_bag_fee)
    total_cost = flight_cost + piloting_cost + gate_and_boarding_fees + passenger_cost + baggage_cost + amenity_cost + internationaltravelfee

    st.subheader("Itemized Quote")

    # Display the total cost
    st.write(f"Flight cost per hour: **${price_per_hour:,.2f}**")
    st.write(f"Flight cost: **${flight_cost:,.2f}**")
    st.write(f"Piloting cost: **${piloting_cost:,.2f}**")
    st.write(f"Passenger cost: **${passenger_cost:,.2f}**")
    st.write(f"Baggage cost: **${baggage_cost:,.2f}**")
    st.write(f"Amenities cost: **${amenity_cost:,.2f}**")
    st.write(f"Transportation fee: **${transportation_cost:,.2f}**")
    st.write(f"Gate and boarding fees: **${gate_and_boarding_fees:,.2f}**")
    st.write(f"International Travel fee: **${internationaltravelfee:,.2f}**")
    st.write(f"Total cost: **${total_cost:,.2f}**")

    st.text_input("Input contact email")

    st.subheader("Purchase with Credit Card")
    st.write(f"Amount to charge: **${total_cost:,.2f}**")

    creditcard = st.number_input("Credit Card Number", min_value=100000000000000)

    cvv = st.number_input("Credit Card CVV", min_value=100)

    address = st.text_input("Input Address registered with Credit Card")

    # Purchase button
    if st.button(f"Complete Purchase for: **${total_cost:,.2f}**"):
        st.success(f"**${total_cost:,.2f}**" " Charged to credit card: " f"**{creditcard}**")
        st.write("Your charter request has been submitted! We will contact you shortly using " f"**{contactemail}**")
        st.warning("If your flight is international, we will contact you shortly requesting customs and visa verification")

        st.write("Thank you for choosing our charter service!")

    st.subheader("Request Quote")
    with st.expander("Why request a quote?"):
        st.write("Requesting a quote allows you to make edits and also makes more space for customization. This also allows other forms of payment such as cash, and check. Mail-in payments are only allowed for flights booked at least 14 days in advance.")

    paymentoptions = [
        "Pay with credit card option above.",
        "Mail-in credit card information (Must book at least 14 days in advance)",
        "Mail-in cash (Must book at least 14 days in advance, no coins allowed)",
        "Mail-in check written to HyperJets LLC (Must book at least 14 days in advance)"
    ]

    st.selectbox("How to pay", paymentoptions)

    mailing_address = st.text_input("Mailing Address")

    if st.button("Request a quote for a flight from " f"**{departure_airport}**" " to " f"**{arrival_airport}**" " using aircraft " f"**{selected_aircraft}**"):
        st.success("The quote will immediately be sent to " f"**{contactemail}**" " after it is ready")
        with st.expander("Important Email Quote Information"):
            st.write("Pricing: None")
            st.write("Duration: Will be sent to you by email immediately after the quote is prepared by a HyperJets Agent")
            st.write("Duration: May take up to 1 business day to prepare")
            st.write("Customization: Special Requests will be analyzed and added to the quote")
            st.write("Customization: If a request involves alcohol, then valid ID may be requested upon takeoff. If a valid ID is not presented, alcohol will not be provided on the flight, and will not be refunded")
            st.write("Mail-in: Mail-in payments are available only with quote")
            st.write("Mail-in: A document specifying how to pay manually will be attached to the quote")
            st.write("Mail-in: Mail in payments are only available 14 days prior to the flight")
            st.write("Payment Options: Credit Card Information, Check written to HyperJets LLC, and Cash (NO COINS)")
        with st.expander("Information for International Flights"):
            st.write("Customs: Remember, standard international customs policies still apply while flying private")
            st.write("Customs: A valid visa for the purpose of the trip and valid passport are required to fly")
            st.write("Customs: We will contact you via email to request validation regarding visas")
