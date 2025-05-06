import itertools
import matplotlib.pyplot as plt
import matplotlib.colors as mcolors

# Define 14 color gradients as (start_hex, end_hex)
gradients = [
    ("#F7A9A7", "#2C0605"),
    ("#F0A9A1", "#210704"),
    ("#F0AAAA", "#210808"),
    ("#E5A3A3", "#0D0101"),
    ("#FCD4CA", "#320F0C"),
    ("#F0CFC9", "#27130E"),
    ("#F0BDBF", "#260D0E"),
    ("#D6B3BB", "#0A0305"),
    ("#FCD6E1", "#320D15"),
    ("#FFD2CA", "#330E0C"),
    ("#F8BCA9", "#2C0902"),
    ("#F2BBAF", "#260906"),
    ("#F7B0D4", "#2C0219"),
    ("#D5B3C4", "#0A0308"),
]

# Interpolate a single gradient
def interpolate_gradient(start_hex, end_hex, steps=10):
    start_rgb = mcolors.hex2color(start_hex)
    end_rgb = mcolors.hex2color(end_hex)
    return [
        mcolors.to_hex([
            start_rgb[i] + (end_rgb[i] - start_rgb[i]) * t / (steps - 1)
            for i in range(3)
        ])
        for t in range(steps)
    ]

# Generate gradient combinations
def generate_combinations(gradients, r):
    return list(itertools.combinations(gradients, r))

# Visualize a combination of gradients (2 or 3)
def plot_gradient_combination(combination):
    fig, axs = plt.subplots(1, len(combination), figsize=(5 * len(combination), 2))
    if len(combination) == 1:
        axs = [axs]
    for i, (start, end) in enumerate(combination):
        grad = interpolate_gradient(start, end)
        axs[i].imshow([[(mcolors.to_rgb(c)) for c in grad]])
        axs[i].set_title(f"{start} → {end}")
        axs[i].axis('off')
    plt.tight_layout()
    plt.show()

# Generate pairs and triplets
pairs = generate_combinations(gradients, 2)
triplets = generate_combinations(gradients, 3)

print(f"Generated {len(pairs)} pair combinations.")
print(f"Generated {len(triplets)} triplet combinations.")

# Show an example of each
print("\nExample Pair Combination:")
plot_gradient_combination(pairs[0])

print("\nExample Triplet Combination:")
plot_gradient_combination(triplets[0])

