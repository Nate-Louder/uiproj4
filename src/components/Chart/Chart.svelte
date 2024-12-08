<script>
	import { onMount } from 'svelte';
	import Chart from 'chart.js/auto';

	let chartInstance;

	const chartConfig = {
		type: 'line',
		data: {
			labels: [
				'Jan-2023',
				'Feb-2023',
				'Mar-2023',
				'Apr-2023',
				'May-2023',
				'Jun-2023',
				'Jul-2023',
				'Aug-2023',
				'Sep-2023',
				'Oct-2023',
				'Nov-2023',
				'Dec-2023',
				'Jan-2024',
				'Feb-2024',
				'Mar-2024',
				'Apr-2024',
				'May-2024',
				'Jun-2024',
				'Jul-2024',
				'Aug-2024',
				'Sep-2024',
				'Oct-2024',
				'Nov-2024',
				'Dec-2024'
			],
			datasets: [
				{
					label: 'Money Lost',
					data: [
						0, 76, -110, 115, -127, -254, -240, -500, -550, -538, -450, -404, -900, -1130, -1476,
						-1980, -1500, -2145, -2000, -2345, -2470, -2880, -3145, -3500
					],
					backgroundColor: 'red',
					borderColor: 'red',
					borderWidth: 2,
					tension: 0.5
				}
			]
		},
		options: {
			responsive: true,
			plugins: {
				legend: { display: false }, // Removed legend
				title: { display: true, text: 'Monthly Money Loss Over Time', color: 'white' } // White chart title
			},
			scales: {
				x: {
					ticks: {
						color: 'white'
					},
					grid: {
						color: 'rgba(255, 255, 255, 0.1)'
					}
				},
				y: {
					ticks: {
						color: 'white'
					},
					grid: {
						color: 'rgba(255, 255, 255, 0.1)'
					}
				}
			}
		}
	};

	onMount(() => {
		const ctx = document.getElementById('myChart').getContext('2d');
		chartInstance = new Chart(ctx, chartConfig);

		return () => {
			if (chartInstance) chartInstance.destroy();
		};
	});
</script>

<canvas id="myChart" width="400" height="200"></canvas>
