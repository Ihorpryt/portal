<div>
    <canvas id="myChart" bind:this={ctx}></canvas>
</div>
  
  <script>
    import {onMount} from 'svelte'
    import Chart from 'chart.js/auto'

    let ctx;

    onMount(
        async ()=> {

            Chart.defaults.color = '#64748b';
            // Chart.defaults.borderColor = '#f1f5f9';
            // Chart.defaults.backgroundColor	= "#f1f5f9"
            

            new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'],

                    datasets: [{
                        label: 'Completed',
                        data: [4, 2, 3, 2, 4, 0],
                        borderWidth: 0,
                        backgroundColor: 'rgba(0,153,255,0.75)',
                        barPercentage: 0.5,
                        categoryPercentage: 1,
                        order: 0,
                        borderRadius: 5,
                    },{
                        label: 'Scheduled',
                        data: [6, 2, 3, 5, 6, 2],
                        borderWidth: 0,
                        backgroundColor: 'rgba(0,153,255,0.25)',
                        barPercentage: 0.5,
                        categoryPercentage: 1,
                        order:1,
                        borderRadius: 5,
                    },]
                },
                options: {
                    responsive:true,
                    layout: {
                        padding: {
                            top: 20
                        }
                    },
                    elements: {
                        bar: {
                            // borderRadius: 5,
                            // borderSkipped:"left",
                        },
                    },
                    plugins: {
                        legend: {
                            display: false,
                            align: "end",
                            labels: {
                                boxWidth: 12,
                                useBorderRadius: true,
                                borderRadius: 2
                            }
                        },
                    },
                    scales: {
                        y: {
                            
                            border: {
                                display: false,
                            },
                            ticks: {
                                display: false,
                            },
                            beginAtZero: true,
                            grid: {
                                display: false,
                            }
                        },
                        x: {
                            stacked: true,
                            grid: {
                                display: false,
                                
                            }
                        }
                        // y: {
                        //     beginAtZero: true,

                        // },
                    }
                }
                }); 

                
                
        }
    );
  
  </script>
  
