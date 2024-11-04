#include <SFML/Graphics.hpp>

int main()
{
    // Membuat jendela
    sf::RenderWindow window(sf::VideoMode(800, 600), "Animasi Hati");

    // Membuat bentuk hati (contoh sederhana menggunakan lingkaran)
    sf::CircleShape heart(50.f);
    heart.setFillColor(sf::Color::Red);
    heart.setPosition(400, 300);

    // Loop utama
    while (window.isOpen())
    {
        sf::Event event;
        while (window.pollEvent(event))
        {
            if (event.type == sf::Event::Closed)
                window.close();
        }

        // Gerakkan hati ke kanan
        heart.move(1.f, 0.f);

        // Jika hati keluar dari layar, kembalikan ke posisi awal
        if (heart.getPosition().x > 800)
            heart.setPosition(0, 300);

        // Clear screen
        window.clear();

        // Draw the shape
        window.draw(heart);

        // Display what was drawn
        window.display();
    }

    return 0;
}
<!---
Gifari030105/Gifari030105 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
